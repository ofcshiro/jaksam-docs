---
title: "Remove item from trunk"
description: "Elimina ítems del maletero de un vehículo usando solo la matrícula, resolviendo automáticamente el ID completo del inventario."
icon: "car-side"
---

Elimina ítems del maletero de un vehículo usando solo la matrícula, resolviendo automáticamente el ID completo del inventario.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:removeItemFromTrunk(plate, itemName, amount, metadata, slotId)
```

```lua Example
-- Elimina 3 botellas de agua del maletero
local plate = GetVehicleNumberPlateText(vehicle)
local success = exports['jaksam_inventory']:removeItemFromTrunk(plate, 'water', 3)

-- Elimina de un slot específico
local success = exports['jaksam_inventory']:removeItemFromTrunk("ABC 123", 'weapon', 1, nil, 5)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `plate` | string | La matrícula del vehículo |
| `itemName` | string | El nombre del ítem a eliminar |
| `amount` | number | Cuántos ítems eliminar |
| `metadata` | table | Metadata con la que comparar para la eliminación (filtrado opcional) |
| `slotId` | number | Slot específico del que eliminar |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `success` | boolean | True si los ítems se eliminaron correctamente |
| `resultCode` | string | Mensaje de error si la operación falló |
| `notificationType` | string | Tipo de notificación a mostrar al usuario |

### Notas

El vehículo debe existir (vehículo propio en la base de datos o vehículo de NPC actualmente generado). Devuelve false con "vehicle_not_found" si el vehículo no existe.
