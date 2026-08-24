---
title: "Add item to trunk"
description: "Añade ítems al maletero de un vehículo usando solo la matrícula, resolviendo automáticamente el ID completo del inventario."
icon: "car-side"
---

Añade ítems al maletero de un vehículo usando solo la matrícula, resolviendo automáticamente el ID completo del inventario.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:addItemToTrunk(plate, itemName, amount, metadata, slotId)
```

```lua Example
-- Añade 5 botellas de agua al maletero del vehículo
local plate = GetVehicleNumberPlateText(vehicle)
local success, result = exports['jaksam_inventory']:addItemToTrunk(plate, 'water', 5)

if not success then
    print("Failed to add item: " .. result)
end

-- Añade un ítem con metadata
local success = exports['jaksam_inventory']:addItemToTrunk("ABC 123", 'phone', 1, {
    number = "555-0123"
})
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `plate` | string | La matrícula del vehículo |
| `itemName` | string | El nombre del ítem a añadir |
| `amount` | number | Cuántos ítems añadir |
| `metadata` | table | Datos adicionales para el ítem |
| `slotId` | number | Slot específico en el que colocar el ítem |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `success` | boolean | True si los ítems se añadieron correctamente |
| `resultCode` | string | Mensaje de error si la operación falló (por ejemplo, "vehicle_not_found") |
| `notificationType` | string | Tipo de notificación a mostrar al usuario |

### Notas

- Funciona con vehículos propios (aunque no estén generados/en el garaje)
- Funciona con vehículos de NPC (si están actualmente generados)
- Crea automáticamente el inventario del maletero si no existe
- Para vehículos propios, el inventario es persistente (se guarda en la base de datos)
