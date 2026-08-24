---
title: "Jugador perdió la señal"
description: "Se activa del lado del servidor cuando un jugador pierde la señal de un tracker."
icon: "satellite-dish"
---

Este event se activa cuando un jugador pierde la señal de un tracker, porque perdió el item necesario.

```lua Event
AddEventHandler("trackers_creator:playerLostSignalWithTracker", function(playerId, trackerId)

end)
```

### Parámetros

| Nombre        | Tipo de dato | Descripción                        |
| ----------- | --------- | ------------------------------------ |
| `playerId`  | integer   | El ID de servidor del jugador          |
| `trackerId` | integer   | El ID del tracker que perdió la señal      |

## Ejemplo

```lua
RegisterNetEvent("trackers_creator:playerLostSignalWithTracker", function(playerId, trackerId)
    -- Puedes usar cualquier código aquí para obtener datos de la base de datos o hacer lo que necesites
end)
```
