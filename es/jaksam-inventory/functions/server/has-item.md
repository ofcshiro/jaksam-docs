---
title: "Has item"
description: "Comprueba si un inventario tiene un ítem específico."
icon: "circle-check"
---

Comprueba si un inventario tiene un ítem específico.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:hasItem(inventoryId, itemName, quantity)
```

```lua Example
-- Comprueba si el jugador tiene 5 panes
local hasItem = exports['jaksam_inventory']:hasItem(1, 'bread', 5)

if hasItem then
    -- Seguro para eliminar ítems
    exports['jaksam_inventory']:removeItem(1, 'bread', 5)
end
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| number | El ID del inventario a comprobar |
| `itemName` | string | El nombre del ítem a comprobar |
| `quantity` | number | Cuántos ítems comprobar. Por defecto es 1 |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `boolean` | boolean | True si el inventario tiene el ítem, false si no |
