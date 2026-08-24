---
title: "Bouton panique pressé"
description: "Se déclenche côté serveur quand un joueur utilise le bouton panique."
icon: "triangle-exclamation"
---

Cet event se déclenche quand un joueur utilise le bouton panique.

```lua Event
AddEventHandler("trackers_creator:playerPressedPanicButton", function(playerId)

end)
```

### Paramètres

| Nom       | Type de donnée | Description                                              |
| ---------- | --------- | ---------------------------------------------------------- |
| `playerId` | integer   | Le server ID du joueur qui a appuyé sur le bouton panique   |

## Exemple

```lua
RegisterNetEvent("trackers_creator:playerPressedPanicButton", function(playerId)
    local name = GetPlayerName(playerId)
    local plyPed = GetPlayerPed(playerId)
    local coords = GetEntityCoords(plyPed)

    print("Player " .. name .. " pressed panic button in coordinates " .. tostring(coords))
end)
```
