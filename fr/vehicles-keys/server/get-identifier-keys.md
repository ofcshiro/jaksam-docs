---
title: "Get identifier keys"
description: "Récupère toutes les clés de véhicule possédées par un identifier de joueur côté serveur."
icon: "list"
---

```lua Export
exports["vehicles_keys"]:getIdentifierKeys(identifier)
```

### Paramètres

| Nom         | Type de donnée | Description                           |
| ------------ | --------- | ---------------------------------------- |
| `identifier` | string    | L'identifier/la licence du joueur cible       |

## Exemple

```lua
Citizen.CreateThread(function()
    local identifier = "abcedfghj12356"

    local keys = exports["vehicles_keys"]:getIdentifierKeys(identifier)

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
