---
title: "Remove keys from player ID"
description: "Elimina llaves de vehículo de un jugador conectado del lado servidor."
icon: "key"
---

```lua Export
exports["vehicles_keys"]:removeKeysFromPlayerId(playerId, plate)
```

### Parámetros

| Nombre       | Tipo de dato | Descripción                   |
| ---------- | --------- | ---------------------------------- |
| `playerId` | integer   | El ID de servidor del jugador objetivo           |
| `plate`    | string    | La placa del vehículo                      |

## Ejemplo

```lua
RegisterNetEvent("garage:vehicleDeleted", function(playerId, plate)
    exports["vehicles_keys"]:removeKeysFromPlayerId(playerId, plate)
end)
```
