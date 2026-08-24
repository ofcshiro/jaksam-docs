---
title: "Get identifier keys"
description: "Obtén todas las llaves de vehículo propiedad de un identifier de jugador del lado servidor."
icon: "list"
---

```lua Export
exports["vehicles_keys"]:getIdentifierKeys(identifier)
```

### Parámetros

| Nombre         | Tipo de dato | Descripción                           |
| ------------ | --------- | ---------------------------------------- |
| `identifier` | string    | El identifier/licencia del jugador objetivo       |

## Ejemplo

```lua
Citizen.CreateThread(function()
    local identifier = "abcedfghj12356"

    local keys = exports["vehicles_keys"]:getIdentifierKeys(identifier)

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
