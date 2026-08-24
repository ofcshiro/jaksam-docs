---
title: "Get all doors list"
description: "Récupère les données de toutes les portes côté serveur."
icon: "list"
---

```lua Export
exports["doors_creator"]:getAllDoors()
```

### Valeur de retour

Une table avec les données de toutes les portes.

## Exemple

```lua
Citizen.CreateThread(function()
    local doors = exports["doors_creator"]:getAllDoors()

    for k, doorData in pairs(doors) do
        if(doorData.allowedJobs and doorData.allowedJobs["police"]) then
            print(doorData.id .. " is a police door")
        end
    end
end)
```
