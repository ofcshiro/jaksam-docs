---
title: "Get player ID keys"
description: "Récupère toutes les clés de véhicule possédées par un joueur connecté côté serveur."
icon: "list"
---

```lua Export
exports["vehicles_keys"]:getPlayerIdKeys(playerId)
```

### Paramètres

| Nom       | Type de donnée | Description                    |
| ---------- | --------- | ---------------------------------- |
| `playerId` | integer   | L'ID serveur du joueur cible           |

## Exemple

```lua
Citizen.CreateThread(function()
    local playerServerId = 16

    local keys = exports["vehicles_keys"]:getPlayerIdKeys(playerServerId)

    print(ESX.DumpTable(keys))

    --[[
        Exemple de résultat

        {
            ["ABC123"] = {
                ["type"] = "owned",
                ["model"] = -563445643
            },

            ["VEG643"] = {
                ["type"] = "temporary",
                ["model"] = 165445642
            },

            ["AEC613"] = {
                ["type"] = "other_player",
                ["model"] = 1732123
            },
        }
    ]]

end)
```
