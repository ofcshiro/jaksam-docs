---
title: "Show hotbar"
description: "Muestra la interfaz de la hotbar con los primeros 5 slots del inventario del jugador."
icon: "grip"
---

Muestra la interfaz de la hotbar con los primeros 5 slots del inventario del jugador.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:showHotbar()
```

```lua Example
-- Muestra la hotbar
exports['jaksam_inventory']:showHotbar()

-- Muestra la hotbar tras recibir un ítem
AddEventHandler('myScript:itemReceived', function()
    exports['jaksam_inventory']:showHotbar()
end)
```

</CodeGroup>

### Parámetros

Ninguno.

### Valor de retorno

Ninguno. Muestra la interfaz de la hotbar, que se oculta automáticamente después de 2 segundos.

### Notas

- La hotbar muestra los slots 1-5 del inventario del jugador
- Si `config.dynamicHotbar` es true, los slots vacíos al final se ocultan
- La hotbar se oculta automáticamente después de 2 segundos
- Varias llamadas reinician el temporizador de ocultado
