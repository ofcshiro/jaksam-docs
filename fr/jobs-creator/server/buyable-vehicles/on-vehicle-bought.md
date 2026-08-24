---
title: "On vehicle bought"
description: "Se déclenche quand un joueur achète un véhicule depuis un marker de garage achetable."
icon: "car"
---

Se déclenche quand un joueur achète un véhicule depuis un marker de garage achetable.

<CodeGroup>

```lua Event
RegisterNetEvent("jobs_creator:permanent_garage:vehicleBought", function(playerId, markerId, vehicleName, vehicleId)
end)
```

```lua Example
RegisterNetEvent("jobs_creator:permanent_garage:vehicleBought", function(playerId, markerId, vehicleName, vehicleId)
    print("Player ID: " .. playerId .. " bought a " .. vehicleName .. " with ID " .. vehicleId .. " from marker " .. markerId)
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | integer | Server ID du joueur |
| `markerId` | integer | ID du marker |
| `vehicleName` | string | Nom du modèle du véhicule |
| `vehicleId` | integer | ID du véhicule dans la base de données |
