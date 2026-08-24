---
title: "Save dirty inventory"
description: "Guarda un inventario específico en la base de datos si ha sido modificado."
icon: "floppy-disk"
---

Guarda un inventario específico en la base de datos si ha sido modificado.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:saveDirtyInventory(inventoryId)
```

```lua Example
-- Guarda un inventario específico
exports['jaksam_inventory']:saveDirtyInventory('police_stash_1')

-- Guarda el inventario del jugador tras cambios importantes
local success = exports['jaksam_inventory']:saveDirtyInventory(1)
if not success then
    print('Failed to save inventory')
end
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| number | El ID del inventario a guardar |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `success` | boolean | True si el inventario se guardó correctamente |
