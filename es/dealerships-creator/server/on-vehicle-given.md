---
title: "Al entregar un vehículo"
description: "Se activa en el servidor después de que un jugador recibe un vehículo de cualquier forma."
icon: "car"
---

Este event se activa después de que un jugador recibe un vehículo de cualquier forma.

```lua Event
AddEventHandler("dealerships_creator:giveVehicleToPlayerId", function(playerId, vehicleName, plate)

end)
```

### Parámetros

| Nombre          | Tipo de dato | Descripción                                   |
| ------------- | --------- | -------------------------------------------------- |
| `playerId`    | integer   | El server ID del jugador que recibió el vehículo          |
| `vehicleName` | string    | El nombre de spawn del vehículo                                |
| `plate`       | string    | La placa del vehículo                                    |

## Ejemplo

```lua
AddEventHandler("dealerships_creator:giveVehicleToPlayerId", function(playerId, vehicleName, plate)
    -- Haz lo que quieras
end)
```
