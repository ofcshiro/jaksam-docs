---
title: "Are hotkeys enabled"
description: "Devuelve si los hotkeys están actualmente habilitados o deshabilitados."
icon: "keyboard"
---

Devuelve si los hotkeys están actualmente habilitados o deshabilitados.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:areHotkeysEnabled()
```

```lua Example
-- Comprueba si los hotkeys están habilitados
local enabled = exports['jaksam_inventory']:areHotkeysEnabled()

if enabled then
    print('Hotkeys are enabled')
else
    print('Hotkeys are disabled')
end

-- Alterna los hotkeys
local currentState = exports['jaksam_inventory']:areHotkeysEnabled()
exports['jaksam_inventory']:setHotkeysEnabled(not currentState)
```

</CodeGroup>

### Parámetros

Ninguno.

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `enabled` | boolean | True si los hotkeys están habilitados, false si están deshabilitados |
