---
title: "Vehicle repaired"
description: "Se dispara después de que un vehículo se repara mediante el menú de acciones de job, útil para añadir lógica de reparación adicional."
icon: "wrench"
---

Se dispara después de reparar un vehículo con el menú de acciones de job. Útil si quieres añadir una función de reparación adicional a las ya existentes.

```lua Event
AddEventHandler("jobs_creator:vehicleRepaired", function(vehicle)
    -- Aquí puedes añadir las funciones de reparación adicionales
end)
```

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `vehicle` | vehicle handle | El handle del vehículo |
