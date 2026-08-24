---
title: "Add ped to selling blacklist"
description: "Evita que se le pueda vender drogas a un ped concreto, por ejemplo tenderos o dealers."
icon: "user-slash"
---

Añade un ped a la blacklist de venta a NPCs, de forma que los jugadores no puedan venderle a ese ped (ejemplo: crupieres de blackjack, tenderos, etc.).

<Note>
  Si prefieres una forma más sencilla, puedes poner en blacklist modelos de ped enteros en `drugs_creator/integrations/cl_integrations.lua`.
</Note>

```lua Export
exports["drugs_creator"]:addPedToNPCSellingBlacklist(ped)
```

### Parámetros

| Nombre  | Tipo de dato       | Descripción             |
| ----- | ---------------- | -------------------------- |
| `ped` | ped (integer)     | El handle del ped objetivo       |

## Ejemplo

```lua
RegisterNetEvent('drugs_creator:framework:ready', function()
    local closestPed = ESX.Game.GetClosestPed()

    exports["drugs_creator"]:addPedToNPCSellingBlacklist(closestPed)
end)
```
