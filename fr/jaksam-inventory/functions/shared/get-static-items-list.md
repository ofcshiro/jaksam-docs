---
title: "Get static items list"
description: "Retourne la liste de tous les items de l'inventaire."
icon: "list"
---

Retourne la liste de tous les items de l'inventaire.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getStaticItemsList()
```

```lua Example
local items = exports['jaksam_inventory']:getStaticItemsList()
local weaponsCount = 0
for itemName, item in pairs(items) do
    if item.type == 'weapon' then
        weaponsCount = weaponsCount + 1
    end
end
print("There are in total " .. weaponsCount .. " registered weapons in the inventory")
```

</CodeGroup>

### Paramètres

Aucun.

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `items` | table | La liste des items, la clé est le nom de l'item, la valeur est l'information de l'item (label, maxStack, weight, stackable, description, rarity, type, etc.) |
