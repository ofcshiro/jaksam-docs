---
title: "Save dirty inventory"
description: "Sauvegarde un inventaire spécifique en base de données s'il a été modifié."
icon: "floppy-disk"
---

Sauvegarde un inventaire spécifique en base de données s'il a été modifié.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:saveDirtyInventory(inventoryId)
```

```lua Example
-- Sauvegarde un inventaire spécifique
exports['jaksam_inventory']:saveDirtyInventory('police_stash_1')

-- Sauvegarde l'inventaire du joueur après des changements importants
local success = exports['jaksam_inventory']:saveDirtyInventory(1)
if not success then
    print('Failed to save inventory')
end
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| number | L'ID de l'inventaire à sauvegarder |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `success` | boolean | True si l'inventaire a été sauvegardé avec succès |
