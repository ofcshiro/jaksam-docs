---
title: "Dequip weapon"
description: "Déséquipe l'arme actuellement équipée."
icon: "gun"
---

Déséquipe l'arme actuellement équipée.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:dequipWeapon(skipSync)
```

```lua Example
-- Déséquipe l'arme
exports['jaksam_inventory']:dequipWeapon()

-- Déséquipe l'arme sans synchroniser les munitions avec le serveur
exports['jaksam_inventory']:dequipWeapon(true)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `skipSync` | boolean | Si true, l'arme sera déséquipée sans synchroniser les munitions avec le serveur |

### Valeur de retour

Aucune. Déséquipe l'arme actuellement équipée.
