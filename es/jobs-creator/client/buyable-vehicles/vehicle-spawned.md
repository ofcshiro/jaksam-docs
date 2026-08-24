---
title: "Vehicle spawned"
description: "Se dispara después de que aparece un vehículo comprado desde el garage de vehículos comprables."
icon: "car"
---

Se dispara después de la aparición de un vehículo comprado desde el garage de vehículos comprables.

<CodeGroup>

```lua Event
AddEventHandler("jobs_creator:permanent_garage:vehicleSpawned", function(vehicle, vehicleName, vehiclePlate)
end)
```

```lua Example
AddEventHandler("jobs_creator:permanent_garage:vehicleSpawned", function(vehicle, vehicleName, vehiclePlate)
    -- Ejemplo para dar las llaves del vehículo (puedes tener un TriggerEvent para usar, eso depende de ti)
    giveKeysToVehicle(vehicle)
    print(vehicleName) -- Ejemplo de salida 'adder'
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `vehicle` | vehicle handle | El handle del vehículo |
| `vehicleName` | string | El nombre del vehículo |
| `vehiclePlate` | string | La matrícula del vehículo |
