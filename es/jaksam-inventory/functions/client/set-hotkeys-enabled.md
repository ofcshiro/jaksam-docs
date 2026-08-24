---
title: "Set hotkeys enabled"
description: "Habilita o deshabilita la funcionalidad de los hotkeys (slots 1-5). Útil, por ejemplo, durante minijuegos o cutscenes."
icon: "keyboard"
---

Habilita o deshabilita la funcionalidad de los hotkeys (slots 1-5). Útil, por ejemplo, durante minijuegos o cutscenes. No olvides volver a habilitar los hotkeys cuando termines.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:setHotkeysEnabled(enabled)
```

```lua Example
-- Deshabilita los hotkeys
exports['jaksam_inventory']:setHotkeysEnabled(false)

-- Habilita los hotkeys
exports['jaksam_inventory']:setHotkeysEnabled(true)

-- Deshabilita los hotkeys durante un minijuego
exports['jaksam_inventory']:setHotkeysEnabled(false)
-- ... código del minijuego ...
exports['jaksam_inventory']:setHotkeysEnabled(true)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `enabled` | boolean | Si es true, los hotkeys se habilitarán y funcionarán normalmente. Si es false, los hotkeys se deshabilitarán y pulsar 1-5 se ignorará |

### Valor de retorno

Ninguno.
