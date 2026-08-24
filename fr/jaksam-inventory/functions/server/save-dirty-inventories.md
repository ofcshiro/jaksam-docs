---
title: "Save dirty inventories"
description: "Sauvegarde tous les inventaires modifiés en base de données."
icon: "floppy-disk"
---

Sauvegarde tous les inventaires modifiés en base de données.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:saveDirtyInventories()
```

```lua Example
-- Sauvegarde tous les inventaires modifiés
exports['jaksam_inventory']:saveDirtyInventories()

-- Bonne pratique : sauvegarder avant le redémarrage du serveur
AddEventHandler('onResourceStop', function(resourceName)
    if resourceName == GetCurrentResourceName() then
        exports['jaksam_inventory']:saveDirtyInventories()
    end
end)
```

</CodeGroup>

### Paramètres

Aucun.

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `success` | boolean | True si tous les inventaires ont été sauvegardés avec succès |
