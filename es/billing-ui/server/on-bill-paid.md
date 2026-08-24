---
title: "On bill paid"
description: "Se dispara del lado del servidor después de pagar una factura."
icon: "circle-check"
---

Este event se dispara después de pagar una factura.

```lua Event
RegisterNetEvent("billing_ui:onBillPaid", function(billId, senderIdentfier, targetIdentifier, amount, date, unixDate)

end)
```

### Parámetros

| Nombre               | Tipo de dato | Descripción                                    |
| ------------------- | --------- | ---------------------------------------------------- |
| `billId`             | integer   | El ID de la factura                                             |
| `senderIdentfier`    | string    | Identificador del remitente de la factura                                   |
| `targetIdentifier`   | string    | Identificador del receptor de la factura                                  |
| `amount`             | integer   | Importe de la factura pagada                                    |
| `date`               | integer   | Fecha en que se creó la factura, en formato legible                 |
| `unixDate`           | integer   | Fecha en tiempo unix                                            |
