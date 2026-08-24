---
title: "Manually sell to a NPC"
description: "Démarre manuellement une vente de drogue à un ped spécifique."
icon: "hand-holding"
---

Event pour démarrer une vente à un PNJ, comme si tu avais appuyé sur E pour vendre via la méthode par défaut.

```lua Event
TriggerEvent("drugs_creator:sellToNPC", ped)
```

### Paramètres

| Nom  | Type de donnée       | Description             |
| ----- | ---------------- | -------------------------- |
| `ped` | ped (integer)     | Le handle du ped ciblé       |

## Exemple

```lua
local closestPed = ESX.Game.GetClosestPed()

TriggerEvent("drugs_creator:sellToNPC", closestPed)
```
