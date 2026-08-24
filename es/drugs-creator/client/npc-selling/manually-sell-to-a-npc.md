---
title: "Manually sell to a NPC"
description: "Inicia manualmente una venta de droga a un ped concreto."
icon: "hand-holding"
---

Event para iniciar la venta a un NPC, tal como ocurriría al pulsar E para vender en el método por defecto.

```lua Event
TriggerEvent("drugs_creator:sellToNPC", ped)
```

### Parámetros

| Nombre  | Tipo de dato       | Descripción             |
| ----- | ---------------- | -------------------------- |
| `ped` | ped (integer)     | El handle del ped objetivo       |

## Ejemplo

```lua
local closestPed = ESX.Game.GetClosestPed()

TriggerEvent("drugs_creator:sellToNPC", closestPed)
```
