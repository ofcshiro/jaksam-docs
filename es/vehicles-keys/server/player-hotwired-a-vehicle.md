---
title: "Player hotwired a vehicle"
description: "Se activa del lado servidor cuando se puentea un vehículo."
icon: "bolt"
---

Se activa cuando se ha puenteado un vehículo.

```lua Event
RegisterNetEvent("vehicles_keys:playerHotwiredVehicle", function(playerId, vehicleNetId)

end)
```

### Parámetros

| Nombre           | Tipo de dato | Descripción         |
| -------------- | --------- | ---------------------- |
| `playerId`     | integer   | ID de servidor del jugador          |
| `vehicleNetId` | integer   | ID de red del vehículo          |

## Ejemplo

```lua
RegisterNetEvent("vehicles_keys:playerHotwiredVehicle", function(playerId, vehicleNetId)
    local vehicle = NetworkGetEntityFromNetworkId(vehicleNetId)

    print("The player " .. GetPlayerName(playerId) .. " has just hotwired a vehicle with model " .. GetEntityModel(vehicle))
end)
```

<Note>
  Coloca este código en el archivo `integrations/sv_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
