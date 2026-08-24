---
title: "Payer une facture"
description: "Paie une facture via son ID, par exemple depuis un script externe."
icon: "credit-card"
---

Déclencheur pour payer correctement une facture via son ID — tu peux l'utiliser depuis des scripts externes.

```lua Event
TriggerServerEvent("billing_ui:payInvoice", billId)
```

### Paramètres

| Nom     | Type de donnée | Description                                                  |
| -------- | --------- | ------------------------------------------------------------- |
| `billId` | integer   | L'ID de la facture (depuis la table `billing` de la base de données)                 |
