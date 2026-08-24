---
title: "Open inventory"
description: "Abre un inventario junto al inventario del jugador."
icon: "door-open"
---

Abre un inventario junto al inventario del jugador.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:openInventory(inventoryId)
```

```lua Example
-- Abre un inventario de tipo stash
exports['jaksam_inventory']:openInventory('police_stash_1')

-- Abre un inventario de maletero
exports['jaksam_inventory']:openInventory('car_trunk_123')
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string | El ID del inventario a abrir |

### Valor de retorno

Ninguno. Abre la interfaz del inventario si tiene éxito.
