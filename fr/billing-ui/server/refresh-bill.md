---
title: "Refresh bill"
description: "Rafraîchit les données d'une facture côté serveur après l'avoir modifiée directement en base de données."
icon: "rotate"
---

Cet export rafraîchit l'ID de facture spécifié, donc si tu modifies les valeurs en base de données, tu peux utiliser cet export pour voir les changements sans redémarrer le script.

<Note>
  Si tu dois supprimer une facture, utilise plutôt l'export [delete bill](/fr/billing-ui/server/delete-bill).
</Note>

```lua Export
exports["billing_ui"]:refreshBillId(billId)
```

### Paramètres

| Nom     | Type de donnée | Description                                                    |
| -------- | --------- | ------------------------------------------------------------------ |
| `billId` | integer   | L'ID de la facture, présent dans la table `billing` de la base de données                    |

## Exemple

```lua
-- Exemple de commande /refreshBillId 51
RegisterCommand("refreshBillId", function(playerId, args)
    local billId = tonumber(args[1])
    exports["billing_ui"]:refreshBillId(billId)
end)
```
