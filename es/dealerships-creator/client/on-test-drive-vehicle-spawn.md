---
title: "Al generar el vehículo de prueba"
description: "Se activa en el cliente después de generar un vehículo de prueba."
icon: "car-side"
---

Este event se activa después de que se genera un vehículo de prueba en el cliente que está haciendo la prueba de manejo.

```lua Event
AddEventHandler("dealerships_creator:testDrive:vehicleSpawned", function(vehicle, vehicleNetId, plate)

end)
```

### Parámetros

| Nombre         | Tipo de dato | Descripción               |
| -------------- | --------- | ---------------------------- |
| `vehicle`      | integer   | El handle del vehículo             |
| `vehicleNetId` | integer   | El ID de red del vehículo          |
| `plate`        | string    | La placa del vehículo             |

## Ejemplo

```lua
AddEventHandler("dealerships_creator:testDrive:vehicleSpawned", function(vehicle, vehicleNetId, plate)
    SetVehicleFuelLevel(vehicle, 100.0)

    -- Puede que quieras dar las llaves del vehículo de alguna forma
end)
```
