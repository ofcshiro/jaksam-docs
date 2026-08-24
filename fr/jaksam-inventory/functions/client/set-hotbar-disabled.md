---
title: "Set hotbar disabled"
description: "Active ou désactive le fonctionnement de la hotbar. Utile par exemple pendant des minijeux."
icon: "grip-lines"
---

Active ou désactive le fonctionnement de la hotbar. Utile par exemple pendant des minijeux. N'oublie pas de réactiver la hotbar une fois terminé.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:setHotbarDisabled(disabled)
```

```lua Example
-- Désactive la hotbar
exports['jaksam_inventory']:setHotbarDisabled(true)

-- Active la hotbar
exports['jaksam_inventory']:setHotbarDisabled(false)

-- Désactive la hotbar pendant une cinématique
exports['jaksam_inventory']:setHotbarDisabled(true)
-- ... code de la cinématique ...
exports['jaksam_inventory']:setHotbarDisabled(false)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `disabled` | boolean | Si true, la hotbar sera désactivée et les appels à `showHotbar()` seront ignorés. Si false, la hotbar sera activée et fonctionnera normalement |

### Valeur de retour

Aucune.
