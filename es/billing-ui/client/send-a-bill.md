---
title: "Send a bill"
description: "Envía una factura a un jugador objetivo."
icon: "paper-plane"
---

Trigger para enviar una factura a un jugador objetivo.

```lua Event
TriggerServerEvent("billing_ui:sendBill", targetId, societyName, reason, amount)
```

### Parámetros

| Nombre          | Tipo de dato | Descripción                                                    |
| ------------- | --------- | ------------------------------------------------------------------ |
| `targetId`    | integer   | ID de servidor del jugador objetivo                                              |
| `societyName` | string    | Nombre de la sociedad (recibirá el dinero de la factura pagada)          |
| `reason`      | string    | El motivo de la factura                                             |
| `amount`      | integer   | El importe de la factura                                             |

## Ejemplo

```lua
local closestPlayer, closestDist = ESX.Game.GetClosestPlayer()
local targetId = GetPlayerServerId(closestPlayer)
local societyName = "society_police"
local reason = "Speed limit"
local amount = 500

TriggerServerEvent("billing_ui:sendBill", targetId, societyName, reason, amount)
```
