---
title: "Ouvrir le menu de facturation"
description: "Ouvre directement le menu de facturation pour une cible connue, sans obliger le joueur à en cliquer une."
icon: "file-invoice-dollar"
---

Déclencheur pour ouvrir le menu de facturation sans obliger le joueur à sélectionner le joueur cible avec la souris.

```lua Event
TriggerEvent("billing_ui:openBillingMenu", targetServerID)
```

### Paramètres

| Nom             | Type de donnée | Description                  |
| ----------------- | --------- | -------------------------------- |
| `targetServerID`  | integer   | Server ID de la cible, ou `nil`         |

## Exemple

```lua
local closestPlayer = ESX.Game.GetClosestPlayer()
local targetPlayerId = GetPlayerServerId(closestPlayer)

TriggerEvent("billing_ui:openBillingMenu", targetPlayerId)
```
