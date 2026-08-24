---
title: "Create bill"
description: "Crea una nueva factura para un jugador o sociedad del lado del servidor."
icon: "file-circle-plus"
---

```lua Export
exports["billing_ui"]:createBill(senderIdentifier, targetIdentifier, reason, amount, target, targetType)
```

### Parámetros

| Nombre                | Tipo de dato | Descripción                                                                                                                                                              |
| -------------------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `senderIdentifier`   | string    | El identificador del jugador que crea la factura. **En QBCore es el citizen ID.**                                                                                        |
| `targetIdentifier`   | string    | El identificador del jugador que recibe la factura. **En QBCore es el citizen ID.**                                                                                       |
| `reason`             | string    | El motivo de la factura                                                                                                                                                        |
| `amount`             | integer   | El importe de la factura                                                                                                                                                          |
| `target`             | string    | Quién recibirá el pago de la factura. Si `targetType` es `player`, el target es un identificador (o citizen ID en QBCore). Si `targetType` es `society`, el target es, por ejemplo, `society_police`. |
| `targetType`         | string    | `player` o `society`                                                                                                                                                                |

## Ejemplo

```lua
-- Ejemplo con ESX
RegisterCommand("sendInvoiceToOfflinePlayer", function(playerId, args)
    local senderIdentifier = ESX.GetPlayerFromId(playerId).identifier
    local targetIdentifier = args[1] -- Ejemplo 6833b871ee066492978077ef154480366a2374b
    local reason = args[2] -- Ejemplo "Speed limit exceeded"
    local amount = tonumber(args[3]) -- Ejemplo 5000
    local target = "society_police"
    local targetType = "society"

    exports["billing_ui"]:createBill(senderIdentifier, targetIdentifier, reason, amount, target, targetType)
end)

-- Ejemplo con QBCore
RegisterCommand("sendInvoiceToOfflinePlayer", function(playerId, args)
    local senderIdentifier = QBCore.Functions.GetPlayer(playerId).PlayerData.citizenid
    local targetIdentifier = args[1] -- Ejemplo GPI46753
    local reason = args[2] -- Ejemplo "Speed limit exceeded"
    local amount = tonumber(args[3]) -- Ejemplo 5000
    local target = "society_police"
    local targetType = "society"

    exports["billing_ui"]:createBill(senderIdentifier, targetIdentifier, reason, amount, target, targetType)
end)
```
