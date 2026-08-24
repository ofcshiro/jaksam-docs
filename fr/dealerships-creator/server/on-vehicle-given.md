---
title: "À la remise d'un véhicule"
description: "Se déclenche côté serveur après qu'un joueur reçoit un véhicule de quelque façon que ce soit."
icon: "car"
---

Cet event se déclenche après qu'un joueur reçoit un véhicule de quelque façon que ce soit.

```lua Event
AddEventHandler("dealerships_creator:giveVehicleToPlayerId", function(playerId, vehicleName, plate)

end)
```

### Paramètres

| Nom          | Type de donnée | Description                                   |
| ------------- | --------- | -------------------------------------------------- |
| `playerId`    | integer   | Le server ID du joueur qui a reçu le véhicule          |
| `vehicleName` | string    | Le nom de spawn du véhicule                                |
| `plate`       | string    | La plaque du véhicule                                    |

## Exemple

```lua
AddEventHandler("dealerships_creator:giveVehicleToPlayerId", function(playerId, vehicleName, plate)
    -- Fais ce que tu veux
end)
```
