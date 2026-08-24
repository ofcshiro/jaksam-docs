---
title: "Pay a bill"
description: "Paga una factura mediante su ID, por ejemplo desde un script externo."
icon: "credit-card"
---

Trigger para pagar correctamente una factura mediante su ID — puedes usar esto desde scripts externos.

```lua Event
TriggerServerEvent("billing_ui:payInvoice", billId)
```

### Parámetros

| Nombre     | Tipo de dato | Descripción                                                  |
| -------- | --------- | ------------------------------------------------------------- |
| `billId` | integer   | El ID de la factura (de la tabla de la base de datos `billing`)                 |
