---
title: "On bill created"
description: "Se déclenche côté serveur après la création d'une facture."
icon: "file-invoice"
---

Cet event se déclenche après la création d'une facture.

```lua Event
RegisterNetEvent("billing_ui:onBillCreated", function(billId, senderIdentfier, targetIdentifier, amount, date, unixDate)

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
