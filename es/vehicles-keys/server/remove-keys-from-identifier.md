---
title: "Remove keys from identifier"
description: "Elimina llaves de vehículo de un identifier de jugador del lado servidor."
icon: "key"
---

```lua Export
exports["vehicles_keys"]:removeKeysFromIdentifier(identifier, plate)
```

### Parámetros

| Nombre         | Tipo de dato | Descripción                     |
| ------------ | --------- | ----------------------------------- |
| `identifier` | string    | El identifier del jugador objetivo           |
| `plate`      | string    | La placa del vehículo                       |

## Ejemplo

```lua
RegisterNetEvent("garage:vehicleDeleted", function(playerId, plate)
    local xPlayer = ESX.GetPlayerFromId(playerId)
    local identifier = xPlayer.identifier

    exports["vehicles_keys"]:removeKeysFromIdentifier(identifier, plate)
end)
```
