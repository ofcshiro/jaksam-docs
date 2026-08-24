---
title: "Get door ID data"
description: "Obtén los datos de una puerta del lado servidor por su ID."
icon: "door-closed"
---

```lua Export
exports["doors_creator"]:getDoorIdData(doorId)
```

### Parámetros

| Nombre     | Tipo de dato | Descripción                   |
| -------- | --------- | -------------------------------- |
| `doorId` | integer   | El ID de la puerta del que obtener los datos    |

## Ejemplo

```lua
Citizen.CreateThread(function()
    local doorId = 55
    local doorData = exports["doors_creator"]:getDoorIdData(doorId)

    print("The name of door " .. doorId .. " is " .. doorData.label)
end)
```
