---
title: "Get door ID data"
description: "Récupère les données d'une porte côté serveur par son ID."
icon: "door-closed"
---

```lua Export
exports["doors_creator"]:getDoorIdData(doorId)
```

### Paramètres

| Nom     | Type de donnée | Description                   |
| -------- | --------- | -------------------------------- |
| `doorId` | integer   | L'ID de la porte dont récupérer les données    |

## Exemple

```lua
Citizen.CreateThread(function()
    local doorId = 55
    local doorData = exports["doors_creator"]:getDoorIdData(doorId)

    print("The name of door " .. doorId .. " is " .. doorData.label)
end)
```
