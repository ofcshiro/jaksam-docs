---
title: "Set inventory max weight"
description: "Establece la capacidad máxima de peso de un inventario."
icon: "weight-hanging"
---

Establece la capacidad máxima de peso de un inventario.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:setInventoryMaxWeight(inventoryId, maxWeight)
```

```lua Example
-- Establece el peso máximo del inventario del jugador
exports['jaksam_inventory']:setInventoryMaxWeight(1, 100)

-- Establece el peso máximo de un stash
exports['jaksam_inventory']:setInventoryMaxWeight('police_stash_1', 500)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| number | El ID del inventario a modificar |
| `maxWeight` | number | La nueva capacidad máxima de peso |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `success` | boolean | True si el peso se estableció correctamente |
