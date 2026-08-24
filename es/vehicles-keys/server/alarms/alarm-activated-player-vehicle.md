---
title: "Alarm activated (player vehicle)"
description: "Se activa del lado servidor cuando se activa una alarma en un vehículo de jugador."
icon: "car"
---

Se activa cuando se activa una alarma en un vehículo de jugador.

```lua Event
RegisterNetEvent("vehicles_keys:alarmOnPlayerVehicle", function(vehicle, vehicleCoords, alarmLevel)

end)
```

### Parámetros

| Nombre            | Tipo de dato | Descripción                       |
| --------------- | --------- | -------------------------------------- |
| `vehicle`       | integer   | Handle del vehículo                            |
| `vehicleCoords` | vector3   | Las coordenadas del vehículo              |
| `alarmLevel`    | integer   | El nivel de la alarma instalada             |

## Ejemplo

```lua
RegisterNetEvent("vehicles_keys:alarmOnPlayerVehicle", function(vehicle, vehicleCoords, alarmLevel)
    -- Puedes añadir una notificación externa si quieres
end)
```

<Note>
  Coloca este código en el archivo `integrations/sv_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
