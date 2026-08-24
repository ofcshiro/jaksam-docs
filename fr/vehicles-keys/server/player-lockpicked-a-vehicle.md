---
title: "Player lockpicked a vehicle"
description: "Se déclenche côté serveur quand un véhicule est crocheté."
icon: "lock-open"
---

Se déclenche quand un véhicule a été crocheté.

```lua Event
RegisterNetEvent("vehicles_keys:playerLockpickedVehicle", function(playerId, vehicleNetId)

end)
```

### Paramètres

| Nom           | Type de donnée | Description         |
| -------------- | --------- | ---------------------- |
| `playerId`     | integer   | ID serveur du joueur          |
| `vehicleNetId` | integer   | ID réseau du véhicule          |

## Exemple

```lua
RegisterNetEvent("vehicles_keys:playerLockpickedVehicle", function(playerId, vehicleNetId)
    local vehicle = NetworkGetEntityFromNetworkId(vehicleNetId)

    print("The player " .. GetPlayerName(playerId) .. " has just lockpicked a vehicle with model " .. GetEntityModel(vehicle))
end)
```

<Note>
  Place ce code dans le fichier `integrations/sv_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
