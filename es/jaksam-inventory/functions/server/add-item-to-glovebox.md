---
title: "Add item to glovebox"
description: "Añade ítems a la guantera de un vehículo usando solo la matrícula, resolviendo automáticamente el ID completo del inventario."
icon: "car"
---

Añade ítems a la guantera de un vehículo usando solo la matrícula, resolviendo automáticamente el ID completo del inventario.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:addItemToGlovebox(plate, itemName, amount, metadata, slotId)
```

```lua Example
-- Añade documentos a la guantera
local plate = GetVehicleNumberPlateText(vehicle)
local success = exports['jaksam_inventory']:addItemToGlovebox(plate, 'documents', 1)

-- Añade varios ítems
local success = exports['jaksam_inventory']:addItemToGlovebox("XYZ 789", 'money', 500)
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
- Crea automáticamente el inventario de la guantera si no existe
- Para vehículos propios, el inventario es persistente (se guarda en la base de datos)
