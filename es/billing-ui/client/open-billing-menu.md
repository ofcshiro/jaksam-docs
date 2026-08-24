---
title: "Open billing menu"
description: "Abre el menú de Billing UI directamente para un objetivo conocido, sin requerir que el jugador haga clic en uno."
icon: "file-invoice-dollar"
---

Trigger para abrir el menú de Billing UI sin requerir que el jugador seleccione al jugador objetivo con el ratón.

```lua Event
TriggerEvent("billing_ui:openBillingMenu", targetServerID)
```

### Parámetros

| Nombre             | Tipo de dato | Descripción                  |
| ----------------- | --------- | -------------------------------- |
| `targetServerID`  | integer   | ID de servidor del objetivo, o `nil`         |

## Ejemplo

```lua
local closestPlayer = ESX.Game.GetClosestPlayer()
local targetPlayerId = GetPlayerServerId(closestPlayer)

TriggerEvent("billing_ui:openBillingMenu", targetPlayerId)
```
