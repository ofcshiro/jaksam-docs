---
title: "Delete door"
description: "Supprime une porte côté serveur par son ID."
icon: "trash"
---

```lua Export
exports["doors_creator"]:deleteDoor(doorId)
```

### Paramètres

| Nom     | Type de donnée | Description                     |
| -------- | --------- | ---------------------------------- |
| `doorId` | integer   | L'ID de la porte à supprimer         |

### Valeur de retour

| Type de donnée | Description                                      |
| --------- | ----------------------------------------------------- |
| boolean   | `true` si la porte a été supprimée, `false` sinon        |

## Exemple

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
