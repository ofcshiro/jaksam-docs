---
title: "Alarm activated (NPC vehicle)"
description: "Se activa del lado servidor cuando se activa una alarma en un vehículo de NPC."
icon: "car-side"
---

Se activa cuando se dispara una alarma en un vehículo de NPC.

```lua Event
RegisterNetEvent("vehicles_keys:alarmOnNPCVehicle", function(vehicle, vehicleCoords)

end)
```

### Parámetros

| Nombre            | Tipo de dato | Descripción                     |
| --------------- | --------- | ------------------------------------ |
| `vehicle`       | integer   | Handle del vehículo                          |
| `vehicleCoords` | vector3   | Las coordenadas del vehículo            |

## Ejemplo

```lua
RegisterNetEvent("vehicles_keys:alarmOnNPCVehicle", function(vehicle, vehicleCoords)
    -- Puedes añadir una notificación externa si quieres
end)
```

<Note>
  Coloca este código en el archivo `integrations/sv_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
