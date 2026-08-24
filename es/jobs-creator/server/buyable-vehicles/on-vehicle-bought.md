---
title: "On vehicle bought"
description: "Se dispara cuando un jugador compra un vehículo en un marcador de garaje comprable."
icon: "car"
---

Se dispara cuando un jugador compra un vehículo en un marcador de garaje comprable.

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

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerId` | integer | ID de servidor del jugador |
| `markerId` | integer | ID del marcador |
| `vehicleName` | string | Nombre del modelo del vehículo |
| `vehicleId` | integer | ID del vehículo en la base de datos |
