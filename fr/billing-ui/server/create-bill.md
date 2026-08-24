---
title: "Create bill"
description: "Crée une nouvelle facture pour un joueur ou une société côté serveur."
icon: "file-circle-plus"
---

```lua Export
exports["billing_ui"]:createBill(senderIdentifier, targetIdentifier, reason, amount, target, targetType)
```

### Paramètres

| Nom                | Type de donnée | Description                                                                                                                                                              |
| -------------------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `senderIdentifier`   | string    | L'identifier du joueur qui crée la facture. **Sur QBCore, c'est le citizen ID.**                                                                                        |
| `targetIdentifier`   | string    | L'identifier du joueur qui reçoit la facture. **Sur QBCore, c'est le citizen ID.**                                                                                       |
| `reason`             | string    | La raison de la facture                                                                                                                                                        |
| `amount`             | integer   | Le montant de la facture                                                                                                                                                          |
| `target`             | string    | Qui recevra le paiement de la facture. Si `targetType` est `player`, la cible est un identifier (ou citizen ID sur QBCore). Si `targetType` est `society`, la cible est par exemple `society_police`. |
| `targetType`         | string    | `player` ou `society`                                                                                                                                                                |

## Exemple

```lua
-- Exemple ESX
RegisterCommand("sendInvoiceToOfflinePlayer", function(playerId, args)
    local senderIdentifier = ESX.GetPlayerFromId(playerId).identifier
    local targetIdentifier = args[1] -- Exemple 6833b871ee066492978077ef154480366a2374b
    local reason = args[2] -- Exemple "Speed limit exceeded"
    local amount = tonumber(args[3]) -- Exemple 5000
    local target = "society_police"
    local targetType = "society"

    exports["billing_ui"]:createBill(senderIdentifier, targetIdentifier, reason, amount, target, targetType)
end)

-- Exemple QBCore
RegisterCommand("sendInvoiceToOfflinePlayer", function(playerId, args)
    local senderIdentifier = QBCore.Functions.GetPlayer(playerId).PlayerData.citizenid
    local targetIdentifier = args[1] -- Exemple GPI46753
    local reason = args[2] -- Exemple "Speed limit exceeded"
    local amount = tonumber(args[3]) -- Exemple 5000
    local target = "society_police"
    local targetType = "society"

    exports["billing_ui"]:createBill(senderIdentifier, targetIdentifier, reason, amount, target, targetType)
end)
```
