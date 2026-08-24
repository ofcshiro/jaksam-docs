---
title: "Vehicle window broken"
description: "Se activa del lado servidor cuando un jugador rompe la ventana de un vehículo."
icon: "car-burst"
---

```lua Event
RegisterNetEvent("vehicles_keys:vehicleWindowBroken", function(playerId, vehicleNetId)

end)
```

### Parámetros

| Nombre           | Tipo de dato | Descripción                              |
| -------------- | --------- | -------------------------------------------- |
| `playerId`     | integer   | El ID de servidor del jugador que rompió la ventana       |
| `vehicleNetId` | integer   | El ID de red del vehículo                             |

## Ejemplo

```lua
RegisterNetEvent("vehicles_keys:vehicleWindowBroken", function(playerId, vehicleNetId)
    local vehicle = NetworkGetEntityFromNetworkId(vehicleNetId)

    print(GetPlayerName(playerId) .. " broke the window of plate " .. GetVehicleNumberPlateText(vehicle))
end)
```
