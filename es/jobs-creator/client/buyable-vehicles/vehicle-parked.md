---
title: "Vehicle parked"
description: "Se dispara después de que un vehículo del garage de vehículos comprables se ha estacionado."
icon: "car"
---

Se dispara después de que el vehículo del garage de vehículos comprables se ha estacionado.

```lua Event
AddEventHandler("jobs_creator:permanent_garage:vehicleParked", function(vehicleModel, vehiclePlate)
end)
```

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `vehicleModel` | integer | El modelo de entidad del vehículo |
| `vehiclePlate` | string | La matrícula del vehículo |
