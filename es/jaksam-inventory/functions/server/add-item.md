---
title: "Add item"
description: "Añade ítems a un inventario con soporte para metadata y colocación en un slot específico."
icon: "cube"
---

Añade ítems a un inventario con soporte para metadata y colocación en un slot específico.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:addItem(inventoryId, itemName, amount, metadata, slotId)
```

```lua Example
-- Añade 5 panes al inventario de un jugador
local success, result = exports['jaksam_inventory']:addItem(1, 'bread', 5)

-- Añade un arma con metadata
local success, result = exports['jaksam_inventory']:addItem(1, 'WEAPON_PISTOL', 1, {
    serial = "ABC123",
    ammo = 12
})

-- Añade un ítem a un slot específico
local success, result = exports['jaksam_inventory']:addItem(1, 'bread', 1, nil, 5) -- slot 5
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| number | El ID del inventario al que añadir ítems. Puede ser el ID de servidor de un jugador o un ID de inventario |
| `itemName` | string | El nombre del ítem a añadir |
| `amount` | number | Cuántos ítems añadir |
| `metadata` | table | Datos adicionales para el ítem (por ejemplo, número de serie del arma, durabilidad del ítem) |
| `slotId` | number | Slot específico en el que colocar el ítem |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `success` | boolean | True si los ítems se añadieron correctamente |
| `resultCode` | string | Mensaje de error si la operación falló |
