---
title: "Get closest door"
description: "Obtén la puerta activa más cercana al jugador."
icon: "door-closed"
---

Devuelve la puerta **activa** más cercana al jugador.

```lua Export
exports["doors_creator"]:getClosestActiveDoor()
```

### Valor de retorno

| Nombre       | Tipo de dato | Descripción                                       |
| ---------- | --------- | ----------------------------------------------------- |
| `door`     | table     | Tabla que contiene `door.id` y `door.object`            |
| `distance` | float     | Distancia a la puerta                                  |

## Ejemplo

```lua
Citizen.CreateThread(function()
    local closestDoor, closestDist = exports["doors_creator"]:getClosestActiveDoor()

    if(closestDoor and closestDist < 3.0) then
        print("The closest door is " .. closestDoor.id .. " and is " .. closestDist .. " meters away")
    end
end)
```
