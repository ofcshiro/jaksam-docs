---
title: "Delete bill"
description: "Elimina una factura del lado del servidor mediante su ID."
icon: "trash"
---

```lua Export
exports["billing_ui"]:deleteBillId(billId)
```

### Parámetros

| Nombre     | Tipo de dato | Descripción                                                    |
| -------- | --------- | ------------------------------------------------------------------ |
| `billId` | integer   | El ID de la factura, que se encuentra en la tabla de la base de datos `billing`                    |

## Ejemplo

```lua
-- Ejemplo de comando /deleteBillId 51
RegisterCommand("deleteBillId", function(playerId, args)
    local billId = tonumber(args[1])
    exports["billing_ui"]:deleteBillId(billId)
end)
```
