---
title: "Get static item"
description: "Récupère les informations génériques d'un item de l'inventaire, comme le poids, si empilable, la description, le label, etc."
icon: "cube"
---

Récupère les informations génériques d'un item de l'inventaire, comme le poids, si empilable, la description, le label, etc.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getStaticItem(itemName)
```

```lua Example
local item = exports['jaksam_inventory']:getStaticItem('bread')
print(item.label) -- Bread
print(item.weight) -- 1.0
print(item.stackable) -- true
print(item.description) -- A bread
print(item.maxStack) -- 100
print(item.rarity) -- common
print(item.type) -- item|container|ammo|currency
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `itemName` | string | Le nom de l'item à récupérer |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `item` | table | Les informations de l'item. Si l'item n'est pas trouvé, retourne nil |
