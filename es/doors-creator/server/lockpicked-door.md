---
title: "Lockpicked door"
description: "Se activa del lado servidor cuando un jugador abre con ganzúa una puerta."
icon: "lock-open"
---

```lua Event
RegisterNetEvent("doors_creator:doorHasBeenLockpicked", function(playerId, doorId)

end)
```

### Parámetros

| Nombre       | Tipo de dato | Descripción                                        |
| ---------- | --------- | ------------------------------------------------------ |
| `playerId` | integer   | El ID de servidor del jugador que abrió la puerta con ganzúa       |
| `doorId`   | integer   | El ID de la puerta que fue abierta con ganzúa                       |

## Ejemplo

```lua
RegisterNetEvent("doors_creator:doorHasBeenLockpicked", function(playerId, doorId)
    local playerName = GetPlayerName(playerId)

    local doorData = exports["doors_creator"]:getDoorIdData(doorId)

    local doorCoords = doorData.coords

    for k, playerId in pairs(GetPlayers()) do
        local xPlayer = ESX.GetPlayerFromId(playerId)

        if(xPlayer.job.name == "police") then
            TriggerClientEvent("alert_system:alert", playerId, doorCoords, "Door has been lockpicked")
        end
    end
end)
```
