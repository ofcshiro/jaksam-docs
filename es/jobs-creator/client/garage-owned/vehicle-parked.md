---
title: "Vehicle parked"
description: "Se dispara después de que un vehículo del garage de vehículos propios se ha estacionado."
icon: "square-parking"
---

Se dispara después de que el vehículo del garage de vehículos propios se ha estacionado.

```lua Event
AddEventHandler("jobs_creator:garage_owned:vehicleParked", function(vehicleModel, vehiclePlate)
end)
```

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `vehicleModel` | integer | El modelo de entidad del vehículo |
| `vehiclePlate` | string | La matrícula del vehículo |
