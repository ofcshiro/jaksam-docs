---
title: "Vehicle window broken"
description: "Se déclenche côté serveur quand un joueur casse la vitre d'un véhicule."
icon: "car-burst"
---

```lua Event
RegisterNetEvent("vehicles_keys:vehicleWindowBroken", function(playerId, vehicleNetId)

end)
```

### Paramètres

| Nom           | Type de donnée | Description                              |
| -------------- | --------- | -------------------------------------------- |
| `playerId`     | integer   | L'ID serveur du joueur qui a cassé la vitre       |
| `vehicleNetId` | integer   | L'ID réseau du véhicule                             |

## Exemple

```lua
RegisterNetEvent("vehicles_keys:vehicleWindowBroken", function(playerId, vehicleNetId)
    local vehicle = NetworkGetEntityFromNetworkId(vehicleNetId)

    print(GetPlayerName(playerId) .. " broke the window of plate " .. GetVehicleNumberPlateText(vehicle))
end)
```
