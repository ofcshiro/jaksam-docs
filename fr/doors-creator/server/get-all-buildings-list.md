---
title: "Get all buildings list"
description: "Récupère les données de tous les bâtiments côté serveur."
icon: "list"
---

```lua Export
exports["doors_creator"]:getAllBuildings()
```

### Valeur de retour

Une table avec les données de tous les bâtiments.

## Exemple

```lua
Citizen.CreateThread(function()
    local buildings = exports["doors_creator"]:getAllBuildings()

    for k, buildingData in pairs(buildings) do
        if(buildingData.allowedJobs and buildingData.allowedJobs["police"]) then
            print(buildingData.label .. " is a police building")
        end
    end
end)
```
