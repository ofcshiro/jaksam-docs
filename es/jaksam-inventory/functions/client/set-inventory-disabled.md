---
title: "Set inventory disabled"
description: "Deshabilita o rehabilita por completo la apertura del inventario, bloqueando hotkeys, keybinds y llamadas directas a exports/eventos."
icon: "ban"
---

Deshabilita o rehabilita por completo la apertura del inventario. Cuando está deshabilitado, se bloquean todas las interacciones con el inventario: hotkeys, keybinds y llamadas directas a exports/eventos. Si el inventario está abierto en el momento de deshabilitarlo, se cerrará y el arma se desequipará automáticamente.

Esto es útil para cutscenes, minijuegos, barras de progreso o cualquier escenario en el que el jugador no deba poder abrir el inventario.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:setInventoryDisabled(disabled)
```

```lua Example
-- Deshabilita el inventario durante una cutscene
exports['jaksam_inventory']:setInventoryDisabled(true)
-- ... código de la cutscene ...
exports['jaksam_inventory']:setInventoryDisabled(false)

-- Deshabilita el inventario durante una barra de progreso
exports['jaksam_inventory']:setInventoryDisabled(true)
-- ... lógica de la barra de progreso ...
exports['jaksam_inventory']:setInventoryDisabled(false)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `disabled` | boolean | Si es true, la apertura del inventario queda completamente bloqueada. Si es false, la apertura del inventario se rehabilita |

### Valor de retorno

Ninguno.

### Notas

**Compatibilidad con ox_inventory:** Si estás migrando desde ox_inventory, este export reemplaza el patrón del state bag `invBusy`. Los scripts que usan `LocalPlayer.state:set('invBusy', true, true)` seguirán funcionando automáticamente, jaksam_inventory escucha los cambios del state bag `invBusy` y los mapea al mismo flag interno.

```lua
-- Patrón de ox_inventory (sigue funcionando con jaksam_inventory)
LocalPlayer.state:set('invBusy', true, true)

-- Export nativo de jaksam_inventory (recomendado)
exports['jaksam_inventory']:setInventoryDisabled(true)
```
