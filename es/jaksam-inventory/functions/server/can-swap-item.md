---
title: "Can swap item"
description: "Comprueba si es posible intercambiar un ítem por otro en un inventario."
icon: "right-left"
---

Comprueba si es posible intercambiar firstItem (eliminando firstItemCount) por testItem (añadiendo testItemCount).

<CodeGroup>

```lua Export
exports['jaksam_inventory']:canSwapItem(inventoryId, firstItem, firstItemCount, testItem, testItemCount)
```

```lua Example
-- Comprueba si el jugador puede intercambiar 5 panes por 1 agua
local playerId = 1
local canSwap = exports['jaksam_inventory']:canSwapItem(playerId, 'bread', 5, 'water', 1)

if canSwap then
    exports['jaksam_inventory']:removeItem(playerId, 'bread', 5)
    exports['jaksam_inventory']:addItem(playerId, 'water', 1)
end
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| number | El ID del inventario a comprobar. Puede ser el ID de servidor de un jugador o un ID de inventario |
| `firstItem` | string | El nombre del ítem a comprobar |
| `firstItemCount` | number | Cuántos ítems eliminar |
| `testItem` | string | El nombre del ítem a añadir |
| `testItemCount` | number | Cuántos ítems añadir |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `boolean` | boolean | True si el inventario puede intercambiar los ítems, false si el intercambio no es posible |
