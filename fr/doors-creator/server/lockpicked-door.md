---
title: "Lockpicked door"
description: "Déclenché côté serveur quand un joueur crochète une porte."
icon: "lock-open"
---

```lua Event
RegisterNetEvent("doors_creator:doorHasBeenLockpicked", function(playerId, doorId)

end)
```

### Paramètres

| Nom       | Type de donnée | Description                                        |
| ---------- | --------- | ------------------------------------------------------ |
| `playerId` | integer   | L'ID serveur du joueur qui a crocheté la porte       |
| `doorId`   | integer   | L'ID de la porte qui a été crochetée                       |

## Exemple

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
