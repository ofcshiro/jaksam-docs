---
title: "Set door ID state (locked/unlocked)"
description: "Verrouille ou déverrouille une porte côté serveur par son ID."
icon: "lock"
---

```lua Export
exports["doors_creator"]:setDoorState(doorId, state)
```

### Paramètres

| Nom     | Type de donnée | Description                               |
| -------- | --------- | ---------------------------------------------- |
| `doorId` | integer   | L'ID de la porte                                       |
| `state`  | integer   | Le nouvel état de la porte. 1 = verrouillé, 0 = déverrouillé      |

## Exemple

```lua
Citizen.CreateThread(function()
    local doors = exports["doors_creator"]:getAllDoors()

    -- This will close ALL the doors
    for k, doorData in pairs(doors) do
        exports["doors_creator"]:setDoorState(doorData.id, 1)
    end
end)
```
