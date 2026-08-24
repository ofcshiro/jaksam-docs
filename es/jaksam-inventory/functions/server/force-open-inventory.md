---
title: "Force open inventory"
description: "Fuerza la apertura de un inventario para un jugador específico sin comprobaciones de permisos."
icon: "door-open"
---

Fuerza la apertura de un inventario para un jugador específico sin comprobaciones de permisos.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:forceOpenInventory(playerId, inventoryId)
```

```lua Example
-- Abre un stash para un jugador
local playerId = 1
exports['jaksam_inventory']:forceOpenInventory(playerId, 'police_stash_1')

-- Abre el inventario de otro jugador (registro/robo)
local targetPlayerId = 2
exports['jaksam_inventory']:forceOpenInventory(playerId, targetPlayerId)

-- Abre un inventario desde un menú/interfaz personalizada
RegisterNetEvent('myresource:openCustomStorage', function(storageId)
    local playerId = source
    exports['jaksam_inventory']:forceOpenInventory(playerId, storageId)
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerId` | number | El ID de servidor del jugador que verá el inventario |
| `inventoryId` | string \| number | El ID del inventario a abrir. Puede ser el ID de servidor de un jugador (number) o un ID de inventario (string) |

### Valor de retorno

Ninguno.
