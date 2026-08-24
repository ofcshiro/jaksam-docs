---
title: "Register usable item"
description: "Enregistre une fonction de callback qui sera appelée lorsqu'un objet est utilisé."
icon: "hand-pointer"
---

Enregistre une fonction de callback qui sera appelée lorsqu'un objet est utilisé. L'enregistrement spécifique au framework fonctionnera quand même, comme `ESX.RegisterUsableItem` et son équivalent QBCore.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:registerUsableItem(itemName, callback)
```

```lua Example: ESX
-- Enregistre un objet utilisable sur ESX
exports['jaksam_inventory']:registerUsableItem('bread', function(playerId, itemName, inventoryItem)
    -- Soigne le joueur lorsque le pain est utilisé
    local plyPed = GetPlayerPed(playerId)
    local health = GetEntityHealth(plyPed)
    SetEntityHealth(plyPed, math.min(health + 20, 200))
end)

-- Enregistre un objet utilisable sur ESX affichant les métadonnées de l'objet utilisé
exports['jaksam_inventory']:registerUsableItem('armour', function(playerId, itemName, inventoryItem)
    print("Armor has still " .. inventoryItem.metadata.value .. "% of durability")
end)
```

```lua Example: QBCore
-- Enregistre un objet utilisable sur QBCore
exports['jaksam_inventory']:registerUsableItem('armour', function(playerId, item)
    print("Armor has still " .. item.metadata.value .. "% of durability")
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `itemName` | string | Le nom de l'objet à enregistrer |
| `callback` | function | Fonction appelée lorsque l'objet est utilisé. Paramètres sur ESX : `playerId, itemName, inventoryItem` (`name`, `metadata`, `amount`). Paramètres sur QBCore : `playerId, inventoryItem` (`name`, `metadata`, `amount`, etc.) |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `success` | boolean | True si l'enregistrement a réussi |
