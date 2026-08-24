---
title: "On bill paid"
description: "Se déclenche côté serveur après le paiement d'une facture."
icon: "circle-check"
---

Cet event se déclenche après le paiement d'une facture.

```lua Event
RegisterNetEvent("billing_ui:onBillPaid", function(billId, senderIdentfier, targetIdentifier, amount, date, unixDate)

end)
```

### Paramètres

| Nom               | Type de donnée | Description                                    |
| ------------------- | --------- | ---------------------------------------------------- |
| `billId`             | integer   | L'ID de la facture                                             |
| `senderIdentfier`    | string    | Identifier de l'expéditeur de la facture                                   |
| `targetIdentifier`   | string    | Identifier du destinataire de la facture                                  |
| `amount`             | integer   | Montant de la facture payée                                    |
| `date`               | integer   | Date de création de la facture, sous forme lisible                 |
| `unixDate`           | integer   | Date en temps unix                                            |
