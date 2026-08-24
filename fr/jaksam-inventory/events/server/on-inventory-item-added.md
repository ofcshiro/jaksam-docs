---
title: "Inventory item added"
description: "Se déclenche quand un item est ajouté avec succès à un inventaire."
icon: "circle-plus"
---

Se déclenche quand un item est ajouté avec succès à un inventaire.

<CodeGroup>

```lua Event
AddEventHandler('jaksam_inventory:onInventoryItemAdded', function(inventoryId, itemName, amount, metadata, slotId)
end)
```

```lua Example
AddEventHandler('jaksam_inventory:onInventoryItemAdded', function(inventoryId, itemName, amount, metadata, slotId)
    local inventoryType = exports['jaksam_inventory']:getInventoryType(inventoryId)
    if inventoryType ~= 'player' then return end -- Ne gère que les inventaires de joueur

    print(string.format("Item %s (x%d) added to inventory %s", itemName, amount, inventoryId))

    -- Pour QBCore : récupère le joueur par son identifiant de personnage
    local Player = exports['qb-core']:GetPlayerByCitizenId(inventoryId)
    if Player then
        local playerId = Player.PlayerData.source
        print(string.format("Player %d added item %s", playerId, itemName))
    end

    -- Pour ESX : récupère le joueur par son identifiant de personnage
    -- local xPlayer = ESX.GetPlayerFromIdentifier(inventoryId)
    -- if xPlayer then
    --     local playerId = xPlayer.source
    --     print(string.format("Player %d added item %s", playerId, itemName))
    -- end
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string | L'identifiant de l'inventaire. Pour les joueurs, c'est l'identifiant du personnage |
| `itemName` | string | Le nom de l'item ajouté |
| `amount` | number | La quantité ajoutée |
| `metadata` | table | Les métadonnées de l'item |
| `slotId` | number \| nil | Le slot où l'item a été ajouté (peut être nil si aucun slot n'était spécifié lors de l'ajout) |
