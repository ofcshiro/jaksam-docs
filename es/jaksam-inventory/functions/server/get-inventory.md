---
title: "Get inventory"
description: "Obtiene los datos completos de un inventario, incluyendo sus ítems, límites de peso y metadata."
icon: "boxes-stacked"
---

Obtiene los datos completos de un inventario, incluyendo sus ítems, límites de peso y metadata.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getInventory(inventoryId)
```

```lua Example
-- Obtiene el inventario de un jugador
local inventory = exports['jaksam_inventory']:getInventory(1) -- jugador con ID de servidor 1

-- Obtiene un inventario de tipo stash
local stashInv = exports['jaksam_inventory']:getInventory('police_stash_1')

if inventory then
    print(inventory.totalWeight) -- imprime el peso actual
    print(inventory.limits.maxWeight) -- imprime el peso máximo permitido
    print(json.encode(inventory.items, {indent = true})) -- {["SLOT-4"] = {name = "itemName", amount = 1, metadata = {}}}
end
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| number | El ID del inventario del que obtener los datos. Puede ser el ID de servidor de un jugador (number) o un ID de inventario (string) |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventory` | table \| nil | `{id, label, type, options, items, totalWeight, limits: {maxSlots, maxWeight}, metadata}` |
