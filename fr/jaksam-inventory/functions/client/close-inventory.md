---
title: "Close inventory"
description: "Ferme l'interface de l'inventaire. Peut soit fermer un inventaire spécifique, soit fermer entièrement l'interface de l'inventaire."
icon: "door-closed"
---

Ferme l'interface de l'inventaire. Peut soit fermer un inventaire spécifique, soit fermer entièrement l'interface de l'inventaire.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:closeInventory(inventoryId)
```

```lua Example
-- Ferme entièrement l'interface de l'inventaire
exports['jaksam_inventory']:closeInventory()

-- Ferme un inventaire spécifique (par ex. une stash)
exports['jaksam_inventory']:closeInventory('police_stash_1')

-- Force la fermeture de l'inventaire après un événement spécifique
AddEventHandler('myScript:forceCloseInventory', function()
    exports['jaksam_inventory']:closeInventory()
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| nil | Si fourni, retire uniquement l'inventaire spécifié de l'interface. Si nil, ferme entièrement l'interface de l'inventaire ainsi que tous les inventaires ouverts |

### Valeur de retour

Aucune.
