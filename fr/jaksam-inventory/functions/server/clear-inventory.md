---
title: "Clear inventory"
description: "Retire tous les objets d'un inventaire, avec possibilité d'exclure certains objets."
icon: "trash"
---

Retire tous les objets d'un inventaire, avec possibilité d'exclure certains objets.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:clearInventory(inventoryId, excludedItems)
```

```lua Example
local playerId = 14

-- Retire tous les objets de l'inventaire du joueur
local success = exports['jaksam_inventory']:clearInventory(playerId)

-- Vide l'inventaire mais garde certains objets
local success = exports['jaksam_inventory']:clearInventory(playerId, 'phone') -- garde le téléphone

-- Vide l'inventaire mais garde plusieurs objets
local success = exports['jaksam_inventory']:clearInventory(1, {'phone', 'id_card', 'driver_license'})

-- Vide l'inventaire d'une stash
local success = exports['jaksam_inventory']:clearInventory('police_stash_1')
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| number | L'ID de l'inventaire à vider. Peut être l'ID serveur d'un joueur ou un ID d'inventaire |
| `excludedItems` | string \| table | Objets à exclure du vidage (à conserver dans l'inventaire). Peut être un seul nom d'objet (string) ou un tableau de noms d'objets (table). Si non fourni, tous les objets seront retirés |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `success` | boolean | True si l'inventaire a été vidé avec succès, false si l'inventaire n'existe pas ou si la mise à jour de la base de données a échoué |
