---
title: "Delete bill"
description: "Supprime une facture côté serveur via son ID."
icon: "trash"
---

```lua Export
exports["billing_ui"]:deleteBillId(billId)
```

### Paramètres

| Nom     | Type de donnée | Description                                                    |
| -------- | --------- | ------------------------------------------------------------------ |
| `billId` | integer   | L'ID de la facture, présent dans la table `billing` de la base de données                    |

## Exemple

```lua
-- Exemple de commande /deleteBillId 51
RegisterCommand("deleteBillId", function(playerId, args)
    local billId = tonumber(args[1])
    exports["billing_ui"]:deleteBillId(billId)
end)
```
