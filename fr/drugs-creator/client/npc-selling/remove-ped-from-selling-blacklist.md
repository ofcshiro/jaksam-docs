---
title: "Remove ped from selling blacklist"
description: "Permet à un ped précédemment blacklisté de recevoir à nouveau des ventes de drogues."
icon: "user-check"
---

Retire un ped de la blacklist de vente aux PNJ — l'opposé de l'export `addPedToNPCSellingBlacklist`.

```lua Export
exports["drugs_creator"]:removePedFromNPCSellingBlacklist(ped)
```

### Paramètres

| Nom  | Type de donnée       | Description             |
| ----- | ---------------- | -------------------------- |
| `ped` | ped (integer)     | Le handle du ped ciblé       |

## Exemple

```lua
RegisterNetEvent('drugs_creator:framework:ready', function()
    local closestPed = ESX.Game.GetClosestPed()

    exports["drugs_creator"]:removePedFromNPCSellingBlacklist(closestPed)
end)
```
