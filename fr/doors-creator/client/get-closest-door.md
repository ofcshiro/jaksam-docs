---
title: "Get closest door"
description: "Récupère la porte active la plus proche du joueur."
icon: "door-closed"
---

Retourne la porte **active** la plus proche du joueur.

```lua Export
exports["doors_creator"]:getClosestActiveDoor()
```

### Valeur de retour

| Nom       | Type de donnée | Description                                       |
| ---------- | --------- | ----------------------------------------------------- |
| `door`     | table     | Table contenant `door.id` et `door.object`            |
| `distance` | float     | Distance par rapport à la porte                                  |

## Exemple

```lua
Citizen.CreateThread(function()
    local closestDoor, closestDist = exports["doors_creator"]:getClosestActiveDoor()

    if(closestDoor and closestDist < 3.0) then
        print("The closest door is " .. closestDoor.id .. " and is " .. closestDist .. " meters away")
    end
end)
```
