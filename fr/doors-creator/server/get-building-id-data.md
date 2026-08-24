---
title: "Get building ID data"
description: "Récupère les données d'un bâtiment côté serveur par son ID."
icon: "building"
---

```lua Export
exports["doors_creator"]:getBuildingIdData(buildingId)
```

### Paramètres

| Nom         | Type de donnée | Description                       |
| ------------ | --------- | ------------------------------------ |
| `buildingId` | integer   | L'ID du bâtiment dont récupérer les données    |

## Exemple

```lua
Citizen.CreateThread(function()
    local buildingId = 55
    local buildingData = exports["doors_creator"]:getBuildingIdData(buildingId)

    print("The name of building " .. buildingId .. " is " .. buildingData.label)
end)
```
