---
title: "Can carry item"
description: "Comprueba si un inventario tiene espacio para ítems adicionales, teniendo en cuenta tanto el peso como los límites de slots."
icon: "weight-hanging"
---

Comprueba si un inventario tiene espacio para ítems adicionales, teniendo en cuenta tanto el peso como los límites de slots.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:canCarryItem(inventoryId, itemName, amount)
```

```lua Example
-- Comprueba si el jugador puede llevar 5 panes
local canCarry = exports['jaksam_inventory']:canCarryItem(1, 'bread', 5)

if canCarry then
    -- Seguro para añadir ítems
    exports['jaksam_inventory']:addItem(1, 'bread', 5)
end
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| number | El ID del inventario a comprobar. Puede ser el ID de servidor de un jugador o un ID de inventario |
| `itemName` | string | El nombre del ítem a comprobar |
| `amount` | number | Cuántos ítems comprobar |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `boolean` | boolean | True si el inventario puede llevar los ítems, false si añadirlos superaría los límites de peso o de slots |
