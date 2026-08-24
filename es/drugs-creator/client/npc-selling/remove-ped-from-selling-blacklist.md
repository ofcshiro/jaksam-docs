---
title: "Remove ped from selling blacklist"
description: "Permite volver a venderle drogas a un ped previamente puesto en blacklist."
icon: "user-check"
---

Elimina un ped de la blacklist de venta a NPCs — lo contrario del export `addPedToNPCSellingBlacklist`.

```lua Export
exports["drugs_creator"]:removePedFromNPCSellingBlacklist(ped)
```

### Parámetros

| Nombre  | Tipo de dato       | Descripción             |
| ----- | ---------------- | -------------------------- |
| `ped` | ped (integer)     | El handle del ped objetivo       |

## Ejemplo

```lua
RegisterNetEvent('drugs_creator:framework:ready', function()
    local closestPed = ESX.Game.GetClosestPed()

    exports["drugs_creator"]:removePedFromNPCSellingBlacklist(closestPed)
end)
```
