---
title: "Set hotkeys enabled"
description: "Active ou désactive le fonctionnement des hotkeys (slots 1-5). Utile par exemple pendant des minijeux ou des cinématiques."
icon: "keyboard"
---

Active ou désactive le fonctionnement des hotkeys (slots 1-5). Utile par exemple pendant des minijeux ou des cinématiques. N'oublie pas de réactiver les hotkeys une fois terminé.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:setHotkeysEnabled(enabled)
```

```lua Example
-- Désactive les hotkeys
exports['jaksam_inventory']:setHotkeysEnabled(false)

-- Active les hotkeys
exports['jaksam_inventory']:setHotkeysEnabled(true)

-- Désactive les hotkeys pendant un minijeu
exports['jaksam_inventory']:setHotkeysEnabled(false)
-- ... code du minijeu ...
exports['jaksam_inventory']:setHotkeysEnabled(true)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `enabled` | boolean | Si true, les hotkeys seront activés et fonctionneront normalement. Si false, les hotkeys seront désactivés et appuyer sur 1-5 sera ignoré |

### Valeur de retour

Aucune.
