---
title: "Set durability"
description: "Establece el valor de durabilidad de un ítem en un slot específico del inventario."
icon: "gauge"
---

Establece el valor de durabilidad de un ítem en un slot específico del inventario.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:setDurability(inventoryId, slotId, durability)
```

```lua Example
-- Establece la durabilidad del arma al 75%
local success, result = exports['jaksam_inventory']:setDurability(1, 5, 75)

-- Reduce la durabilidad tras usar el arma
local item = exports['jaksam_inventory']:getItemFromSlot(playerId, slotId)
if item and item.metadata.durability then
    local newDurability = math.max(0, item.metadata.durability - 5)
    exports['jaksam_inventory']:setDurability(playerId, slotId, newDurability)
end

-- Establece la durabilidad de un ítem en un stash
exports['jaksam_inventory']:setDurability('police_stash_1', 3, 100)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| number | El ID del inventario que contiene el ítem. Puede ser el ID de servidor de un jugador o un ID de inventario |
| `slotId` | number | El slot que contiene el ítem a actualizar |
| `durability` | number | El valor de durabilidad a establecer (se limitará entre 0 y 100) |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `success` | boolean | True si la durabilidad se actualizó correctamente |
| `resultCode` | string | Mensaje de error si la operación falló |
