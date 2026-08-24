---
title: "Get player ID keys"
description: "Obtén todas las llaves de vehículo propiedad de un jugador conectado del lado servidor."
icon: "list"
---

```lua Export
exports["vehicles_keys"]:getPlayerIdKeys(playerId)
```

### Parámetros

| Nombre       | Tipo de dato | Descripción                    |
| ---------- | --------- | ---------------------------------- |
| `playerId` | integer   | El ID de servidor del jugador objetivo           |

## Ejemplo

```lua
Citizen.CreateThread(function()
    local playerServerId = 16

    local keys = exports["vehicles_keys"]:getPlayerIdKeys(playerServerId)

    print(ESX.DumpTable(keys))

    --[[
        Ejemplo de salida

        {
            ["ABC123"] = {
                ["type"] = "owned",
                ["model"] = -563445643
            },

            ["VEG643"] = {
                ["type"] = "temporary",
                ["model"] = 165445642
            },

            ["AEC613"] = {
                ["type"] = "other_player",
                ["model"] = 1732123
            },
        }
    ]]

end)
```
