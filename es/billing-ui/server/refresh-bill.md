---
title: "Refresh bill"
description: "Actualiza los datos de una factura del lado del servidor después de editarla directamente en la base de datos."
icon: "rotate"
---

Este export actualiza la factura especificada mediante su ID, de modo que si editas los valores en la base de datos, puedes usar este export para ver los cambios sin necesidad de reiniciar el script.

<Note>
  Si necesitas eliminar una factura, usa el export [delete bill](/es/billing-ui/server/delete-bill) en su lugar.
</Note>

```lua Export
exports["billing_ui"]:refreshBillId(billId)
```

### Parámetros

| Nombre     | Tipo de dato | Descripción                                                    |
| -------- | --------- | ------------------------------------------------------------------ |
| `billId` | integer   | El ID de la factura, que se encuentra en la tabla de la base de datos `billing`                    |

## Ejemplo

```lua
-- Ejemplo de comando /refreshBillId 51
RegisterCommand("refreshBillId", function(playerId, args)
    local billId = tonumber(args[1])
    exports["billing_ui"]:refreshBillId(billId)
end)
```
