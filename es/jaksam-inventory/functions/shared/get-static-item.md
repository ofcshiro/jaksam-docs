---
title: "Get static item"
description: "Obtiene información genérica de un ítem del inventario, como peso, si es apilable, descripción, label, etc."
icon: "cube"
---

Obtiene información genérica de un ítem del inventario, como peso, si es apilable, descripción, label, etc.

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

### Parámetros

| Nombre | Tipo de Dato | Descripción |
| --- | --- | --- |
| `itemName` | string | El nombre del ítem a obtener |

### Valor de retorno

| Nombre | Tipo de Dato | Descripción |
| --- | --- | --- |
| `item` | table | La información del ítem. Si el ítem no se encuentra, devuelve nil |
