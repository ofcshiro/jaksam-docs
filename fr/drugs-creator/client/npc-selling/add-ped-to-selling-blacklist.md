---
title: "Add ped to selling blacklist"
description: "Empêche la vente de drogues à un ped spécifique, par exemple des commerçants ou des dealers."
icon: "user-slash"
---

Ajoute un ped à la blacklist de vente aux PNJ, afin que les joueurs ne puissent pas lui vendre (exemple : croupiers de blackjack, commerçants, etc.).

<Note>
  Si tu préfères une méthode plus simple, tu peux blacklister des modèles de ped entiers dans `drugs_creator/integrations/cl_integrations.lua`.
</Note>

```lua Export
exports["drugs_creator"]:addPedToNPCSellingBlacklist(ped)
```

### Paramètres

| Nom  | Type de donnée       | Description             |
| ----- | ---------------- | -------------------------- |
| `ped` | ped (integer)     | Le handle du ped ciblé       |

## Exemple

```lua
RegisterNetEvent('drugs_creator:framework:ready', function()
    local closestPed = ESX.Game.GetClosestPed()

    exports["drugs_creator"]:addPedToNPCSellingBlacklist(closestPed)
end)
```
