---
title: "Remove item"
description: "Elimina ítems de un inventario."
icon: "trash"
---

Elimina ítems de un inventario.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:removeItem(inventoryId, itemName, amount, metadata, slotId)
```

```lua Example
-- Elimina 5 panes del inventario del jugador
local success, result = exports['jaksam_inventory']:removeItem(1, 'bread', 5)

-- Elimina un arma específica por metadata
local success, result = exports['jaksam_inventory']:removeItem(1, 'weapon_pistol', 1, {
    serial = "ABC123"
})

-- Elimina de un slot específico
local success, result = exports['jaksam_inventory']:removeItem(1, 'bread', 1, nil, 5)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| number | El ID del inventario del que eliminar ítems. Puede ser el ID de servidor de un jugador o un ID de inventario |
| `itemName` | string | El nombre del ítem a eliminar |
| `amount` | number | Cuántos ítems eliminar |
| `metadata` | table | Metadata con la que comparar al eliminar ítems (si se proporciona, solo se eliminarán los ítems con la misma metadata Y el mismo nombre) |
| `slotId` | number | Slot específico del que eliminar ítems |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `success` | boolean | True si los ítems se eliminaron correctamente |
| `resultCode` | string | Mensaje de error si la operación falló |
