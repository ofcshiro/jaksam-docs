---
title: "Force open inventory"
description: "Force l'ouverture d'un inventaire pour un joueur spécifique sans vérification de permission."
icon: "door-open"
---

Force l'ouverture d'un inventaire pour un joueur spécifique sans vérification de permission.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:forceOpenInventory(playerId, inventoryId)
```

```lua Example
-- Ouvre une stash pour un joueur
local playerId = 1
exports['jaksam_inventory']:forceOpenInventory(playerId, 'police_stash_1')

-- Ouvre l'inventaire d'un autre joueur (fouille/vol)
local targetPlayerId = 2
exports['jaksam_inventory']:forceOpenInventory(playerId, targetPlayerId)

-- Ouvre un inventaire depuis un menu/UI personnalisé
RegisterNetEvent('myresource:openCustomStorage', function(storageId)
    local playerId = source
    exports['jaksam_inventory']:forceOpenInventory(playerId, storageId)
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | number | L'ID serveur du joueur qui verra l'inventaire |
| `inventoryId` | string \| number | L'ID de l'inventaire à ouvrir. Peut être l'ID serveur d'un joueur (number) ou un ID d'inventaire (string) |

### Valeur de retour

Aucune.
