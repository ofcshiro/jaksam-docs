---
title: "Are hotkeys enabled"
description: "Renvoie si les hotkeys sont actuellement activés ou désactivés."
icon: "keyboard"
---

Renvoie si les hotkeys sont actuellement activés ou désactivés.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:areHotkeysEnabled()
```

```lua Example
-- Vérifie si les hotkeys sont activés
local enabled = exports['jaksam_inventory']:areHotkeysEnabled()

if enabled then
    print('Hotkeys are enabled')
else
    print('Hotkeys are disabled')
end

-- Bascule les hotkeys
local currentState = exports['jaksam_inventory']:areHotkeysEnabled()
exports['jaksam_inventory']:setHotkeysEnabled(not currentState)
```

</CodeGroup>

### Paramètres

Aucun.

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `enabled` | boolean | True si les hotkeys sont activés, false s'ils sont désactivés |
