---
title: "Get items by name"
description: "Récupère tous les objets d'un inventaire par nom, avec filtrage optionnel des métadonnées."
icon: "tags"
---

Récupère tous les objets d'un inventaire par nom, avec filtrage optionnel des métadonnées.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemsByName(inventoryId, itemName, metadata, strict)
```

```lua Example
-- Récupère tous les pains dans l'inventaire du joueur
local playerId = 1
local breads = exports['jaksam_inventory']:getItemsByName(playerId, 'bread')

print('Found ' .. #breads .. ' bread stacks')
for i = 1, #breads do
    local bread = breads[i]
    print('Slot ' .. bread.slot .. ': ' .. bread.amount .. ' breads')
end

-- Récupère toutes les armes avec des métadonnées spécifiques (ammo = 0)
local weapons = exports['jaksam_inventory']:getItemsByName(playerId, 'WEAPON_PISTOL', {
    ammo = 0
})

-- Calcule le montant total sur tous les emplacements (il est conseillé d'utiliser getTotalItemAmount à la place)
local totalBread = 0
local allBreads = exports['jaksam_inventory']:getItemsByName(playerId, 'bread')
for i = 1, #allBreads do
    totalBread = totalBread + allBreads[i].amount
end
print('Total bread amount:', totalBread)

-- Retire tout le pain de l'inventaire
local breads = exports['jaksam_inventory']:getItemsByName(playerId, 'bread')
for i = 1, #breads do
    exports['jaksam_inventory']:removeItem(playerId, 'bread', breads[i].amount, nil, breads[i].slot)
end
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| number | L'ID de l'inventaire dans lequel chercher. Peut être l'ID serveur d'un joueur (number) ou un ID d'inventaire (string) |
| `itemName` | string | Le nom des objets à rechercher |
| `metadata` | table | Métadonnées à faire correspondre lors de la recherche. Si fourni, seuls les objets avec des métadonnées correspondantes seront retournés |
| `strict` | boolean | Si la correspondance des métadonnées doit être stricte (par défaut : nil). Si true, tous les champs de métadonnées doivent correspondre exactement |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `items` | table | Tableau de tous les objets trouvés correspondant aux critères (chacun avec `name`, `amount`, `metadata`, `slot`). Table vide `{}` si aucun objet n'est trouvé |

### Notes

- Chaque objet inclut le champ `slot` indiquant où il a été trouvé
- Utilise cette fonction lorsque tu dois traiter plusieurs piles du même objet
- Pour les recherches d'un seul objet, préfère `getItemByName` pour de meilleures performances
