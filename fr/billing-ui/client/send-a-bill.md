---
title: "Envoyer une facture"
description: "Envoie une facture à un joueur cible."
icon: "paper-plane"
---

Déclencheur pour envoyer une facture à un joueur cible.

```lua Event
TriggerServerEvent("billing_ui:sendBill", targetId, societyName, reason, amount)
```

### Paramètres

| Nom          | Type de donnée | Description                                                    |
| ------------- | --------- | ------------------------------------------------------------------ |
| `targetId`    | integer   | Server ID du joueur cible                                              |
| `societyName` | string    | Nom de la société (elle recevra l'argent de la facture payée)          |
| `reason`      | string    | La raison de la facture                                             |
| `amount`      | integer   | Le montant de la facture                                             |

## Exemple

```lua
local closestPlayer, closestDist = ESX.Game.GetClosestPlayer()
local targetId = GetPlayerServerId(closestPlayer)
local societyName = "society_police"
local reason = "Speed limit"
local amount = 500

TriggerServerEvent("billing_ui:sendBill", targetId, societyName, reason, amount)
```
