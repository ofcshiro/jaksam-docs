---
title: "Open inventory"
description: "Ouvre un inventaire aux côtés de l'inventaire du joueur."
icon: "door-open"
---

Ouvre un inventaire aux côtés de l'inventaire du joueur.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:openInventory(inventoryId)
```

```lua Example
-- Ouvre un inventaire de type stash
exports['jaksam_inventory']:openInventory('police_stash_1')

-- Ouvre un inventaire de coffre
exports['jaksam_inventory']:openInventory('car_trunk_123')
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string | L'ID de l'inventaire à ouvrir |

### Valeur de retour

Aucune. Ouvre l'interface de l'inventaire en cas de succès.
