---
title: "Close inventory"
description: "Cierra la interfaz del inventario. Puede cerrar un inventario específico o cerrar toda la interfaz del inventario."
icon: "door-closed"
---

Cierra la interfaz del inventario. Puede cerrar un inventario específico o cerrar toda la interfaz del inventario.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:closeInventory(inventoryId)
```

```lua Example
-- Cierra toda la interfaz del inventario
exports['jaksam_inventory']:closeInventory()

-- Cierra un inventario específico (por ejemplo, un stash)
exports['jaksam_inventory']:closeInventory('police_stash_1')

-- Fuerza el cierre del inventario tras un evento específico
AddEventHandler('myScript:forceCloseInventory', function()
    exports['jaksam_inventory']:closeInventory()
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| nil | Si se proporciona, elimina solo el inventario especificado de la interfaz. Si es nil, cierra toda la interfaz del inventario y todos los inventarios abiertos |

### Valor de retorno

Ninguno.
