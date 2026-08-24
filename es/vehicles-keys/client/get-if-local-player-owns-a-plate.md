---
title: "Get if local player owns a plate"
description: "Comprueba si el jugador local es dueño de una placa de vehículo específica."
icon: "circle-question"
---

Este export se puede usar para saber si **el jugador local** es dueño de una placa de vehículo. También comprobará las compartidas, temporales, etc.

```lua Export
exports["vehicles_keys"]:doesPlayerOwnPlate(plate)
```

### Parámetros

| Nombre    | Tipo de dato | Descripción                  |
| ------- | --------- | -------------------------------- |
| `plate` | string    | La placa del vehículo a comprobar          |

### Valor de retorno

`true` si el vehículo es propio.

`false` si el vehículo no es propio.

## Ejemplo

```lua
RegisterCommand("checkPlate", function(_, args)
    local plate = args[1] -- Ejemplo "ABC 123"

    if(exports["vehicles_keys"]:doesPlayerOwnPlate(plate)) then
        print("I own this vehicle plate")
    else
        print("I DO NOT own this vehicle plate")
    end
end)
```
