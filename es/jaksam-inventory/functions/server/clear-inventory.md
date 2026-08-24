---
title: "Clear inventory"
description: "Elimina todos los ítems de un inventario, con exclusión opcional de ítems específicos."
icon: "trash"
---

Elimina todos los ítems de un inventario, con exclusión opcional de ítems específicos.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:clearInventory(inventoryId, excludedItems)
```

```lua Example
local playerId = 14

-- Elimina todos los ítems del inventario del jugador
local success = exports['jaksam_inventory']:clearInventory(playerId)

-- Vacía el inventario pero conserva un ítem específico
local success = exports['jaksam_inventory']:clearInventory(playerId, 'phone') -- conserva el teléfono

-- Vacía el inventario pero conserva varios ítems
local success = exports['jaksam_inventory']:clearInventory(1, {'phone', 'id_card', 'driver_license'})

-- Vacía un inventario de tipo stash
local success = exports['jaksam_inventory']:clearInventory('police_stash_1')
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| number | El ID del inventario a vaciar. Puede ser el ID de servidor de un jugador o un ID de inventario |
| `excludedItems` | string \| table | Ítems a excluir del vaciado (se conservan en el inventario). Puede ser el nombre de un único ítem (string) o un array de nombres de ítems (table). Si no se proporciona, se eliminarán todos los ítems |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `success` | boolean | True si el inventario se vació correctamente, false si el inventario no existe o falló la actualización de la base de datos |
