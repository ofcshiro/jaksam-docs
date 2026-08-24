---
title: "Get items by name"
description: "Renvoie tous les items correspondant à un nom d'item spécifique dans l'inventaire du joueur, avec leurs numéros de slot."
icon: "tags"
---

Renvoie tous les items correspondant à un nom d'item spécifique dans l'inventaire du joueur. Contrairement à `getItemByName` qui ne renvoie que la première correspondance, cette fonction renvoie toutes les occurrences avec leurs numéros de slot.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemsByName(itemName)
```

```lua Example
-- Récupère tous les items de pain dans l'inventaire
local breadItems = exports['jaksam_inventory']:getItemsByName('bread')

print('Found ' .. #breadItems .. ' bread items')
for i, item in pairs(breadItems) do
    print('Slot ' .. item.slot .. ': ' .. item.amount .. 'x ' .. item.name)
end

-- Vérifie si le joueur possède plusieurs armes du même type
local pistols = exports['jaksam_inventory']:getItemsByName('weapon_pistol')
if #pistols > 1 then
    print('Player has multiple pistols in different slots')
    for i, pistol in pairs(pistols) do
        if pistol.metadata and pistol.metadata.serial then
            print('Serial: ' .. pistol.metadata.serial .. ' in slot ' .. pistol.slot)
        end
    end
end

-- Scénario où aucun item n'est trouvé
local rareItems = exports['jaksam_inventory']:getItemsByName('rare_diamond')
if #rareItems == 0 then
    print('Player has no rare diamonds')
end
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `itemName` | string | Le nom des items à rechercher dans l'inventaire du joueur |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `items` | table | Tableau de tous les items correspondant au nom. Chaque item inclut `name`, `amount`, `metadata` et `slot`. Renvoie un tableau vide si aucun item n'est trouvé |
