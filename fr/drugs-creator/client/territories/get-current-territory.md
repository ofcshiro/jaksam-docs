---
title: "Get current territory"
description: "Récupère le nom du territoire dans lequel se trouve actuellement le joueur local."
icon: "map-pin"
---

Retourne le nom du territoire dans lequel se trouve actuellement le joueur local, ou `nil` si en dehors de tout territoire.

```lua Export
local territoryName = exports["drugs_creator"]:getCurrentTerritory()
```

### Retour

| Type de donnée      | Description                                     |
| --------------- | -------------------------------------------------- |
| string / nil    | Le nom du territoire, ou `nil` si le joueur n'en est dans aucun |

## Exemple

```lua
local territory = exports["drugs_creator"]:getCurrentTerritory()

if territory then
    print("You are in territory: " .. territory)
else
    print("You are not inside any territory")
end
```
