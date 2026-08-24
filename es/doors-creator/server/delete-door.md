---
title: "Delete door"
description: "Elimina una puerta del lado servidor por su ID."
icon: "trash"
---

```lua Export
exports["doors_creator"]:deleteDoor(doorId)
```

### Parámetros

| Nombre     | Tipo de dato | Descripción                     |
| -------- | --------- | ---------------------------------- |
| `doorId` | integer   | El ID de la puerta a eliminar         |

### Valor de retorno

| Tipo de dato | Descripción                                      |
| --------- | ----------------------------------------------------- |
| boolean   | `true` si la puerta fue eliminada, `false` en caso contrario        |

## Ejemplo

```lua
Citizen.CreateThread(function()
    local doorId = 55

    local success = exports["doors_creator"]:deleteDoor(doorId)

    if success then
        print("Door with ID " .. doorId .. " has been removed")
    else
        print("Failed to remove door with ID " .. doorId)
    end
end)
```
