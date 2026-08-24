---
title: "Set hotbar disabled"
description: "Habilita o deshabilita la funcionalidad de la hotbar. Útil, por ejemplo, durante minijuegos."
icon: "grip-lines"
---

Habilita o deshabilita la funcionalidad de la hotbar. Útil, por ejemplo, durante minijuegos. No olvides volver a habilitar la hotbar cuando termines.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:setHotbarDisabled(disabled)
```

```lua Example
-- Deshabilita la hotbar
exports['jaksam_inventory']:setHotbarDisabled(true)

-- Habilita la hotbar
exports['jaksam_inventory']:setHotbarDisabled(false)

-- Deshabilita la hotbar durante una cutscene
exports['jaksam_inventory']:setHotbarDisabled(true)
-- ... código de la cutscene ...
exports['jaksam_inventory']:setHotbarDisabled(false)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `disabled` | boolean | Si es true, la hotbar se deshabilitará y las llamadas a `showHotbar()` se ignorarán. Si es false, la hotbar se habilitará y funcionará normalmente |

### Valor de retorno

Ninguno.
