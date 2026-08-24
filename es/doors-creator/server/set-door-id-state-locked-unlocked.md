---
title: "Set door ID state (locked/unlocked)"
description: "Bloquea o desbloquea una puerta del lado servidor por su ID."
icon: "lock"
---

```lua Export
exports["doors_creator"]:setDoorState(doorId, state)
```

### Parámetros

| Nombre     | Tipo de dato | Descripción                               |
| -------- | --------- | ---------------------------------------------- |
| `doorId` | integer   | El ID de la puerta                                       |
| `state`  | integer   | El nuevo estado de la puerta. 1 = bloqueado, 0 = desbloqueado      |

## Ejemplo

```lua
Citizen.CreateThread(function()
    local doors = exports["doors_creator"]:getAllDoors()

    -- Esto cerrará TODAS las puertas
    for k, doorData in pairs(doors) do
        exports["doors_creator"]:setDoorState(doorData.id, 1)
    end
end)
```
