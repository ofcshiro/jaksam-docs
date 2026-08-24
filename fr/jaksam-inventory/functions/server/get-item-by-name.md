---
title: "Get item by name"
description: "Récupère le premier objet trouvé dans un inventaire par son nom, avec filtrage optionnel des métadonnées."
icon: "tag"
---

Récupère le premier objet trouvé dans un inventaire par son nom, avec filtrage optionnel des métadonnées.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemByName(inventoryId, itemName, metadata)
```

```lua Example
-- Récupère le premier pain dans l'inventaire du joueur
local playerId = 1
local item, slotId = exports['jaksam_inventory']:getItemByName(playerId, 'bread')

if item then
    print('Found bread in slot:', slotId)
    print('Amount in this slot:', item.amount)
    print('Item metadata:', json.encode(item.metadata))
end

-- Récupère une arme avec un numéro de série spécifique
local weapon, weaponSlot = exports['jaksam_inventory']:getItemByName(playerId, 'WEAPON_PISTOL', {
    serial = "ABC123"
})

if weapon then
    print('Found weapon in slot:', weaponSlot)
    print('Weapon ammo:', weapon.metadata.ammo)
end
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| number | L'ID de l'inventaire dans lequel chercher. Peut être l'ID serveur d'un joueur (number) ou un ID d'inventaire (string) |
| `itemName` | string | Le nom de l'objet à rechercher |
| `metadata` | table | Métadonnées à faire correspondre lors de la recherche. Si fourni, seuls les objets avec des métadonnées correspondantes seront retournés |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `item` | table \| nil | Le premier objet trouvé correspondant aux critères, ou nil si non trouvé |
| `slotId` | number \| nil | L'ID brut de l'emplacement où l'objet a été trouvé (index basé sur 1), nil si l'objet n'est pas trouvé |
