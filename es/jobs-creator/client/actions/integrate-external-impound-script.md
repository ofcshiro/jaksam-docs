---
title: "Integrate external impound script"
description: "Conecta tu propio script de depósito de vehículos a Jobs Creator cuando se incauta un vehículo."
icon: "warehouse"
---

Se dispara cuando se incauta un vehículo.

<CodeGroup>

```lua Event
AddEventHandler("jobs_creator:actions:vehicleImpounded", function(vehiclePlate, vehicleModel)
end)
```

```lua Example
RegisterNetEvent("jobs_creator:actions:vehicleImpounded", function(vehiclePlate, vehicleModel)
    -- Aquí puedes añadir los exports de tu script de depósito de vehículos
    TriggerServerEvent("impound_script:impoundVehicle", vehiclePlate, vehicleModel)
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `vehiclePlate` | string | La matrícula del vehículo |
| `vehicleModel` | string | El modelo del vehículo |
