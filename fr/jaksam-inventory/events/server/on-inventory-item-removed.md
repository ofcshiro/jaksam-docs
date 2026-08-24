---
title: "Inventory item removed"
description: "Se déclenche quand un item est retiré avec succès d'un inventaire."
icon: "circle-minus"
---

Se déclenche quand un item est retiré avec succès d'un inventaire.

<CodeGroup>

```lua Event
AddEventHandler('jaksam_inventory:onInventoryItemRemoved', function(inventoryId, itemName, amount, metadata, slotId)
end)
```

```lua Example
AddEventHandler('jaksam_inventory:onInventoryItemRemoved', function(inventoryId, itemName, amount, metadata, slotId)
    local inventoryType = exports['jaksam_inventory']:getInventoryType(inventoryId)
    if inventoryType ~= 'player' then return end -- Ne gère que les inventaires de joueur

    print(string.format("Item %s (x%d) removed from inventory %s", itemName, amount, inventoryId))

    -- Pour QBCore : récupère le joueur par son identifiant de personnage
    local Player = exports['qb-core']:GetPlayerByCitizenId(inventoryId)
    if Player then
        local playerId = Player.PlayerData.source
        print(string.format("Player %d removed item %s", playerId, itemName))

        -- Exemple : enregistrer sur Discord ou en base de données
        -- exports['your_logs']:log({
        --     event = "item_removed",
        --     playerId = playerId,
        --     item = itemName,
        --     amount = amount
        -- })
    end

    -- Pour ESX : récupère le joueur par son identifiant de personnage
    -- local xPlayer = ESX.GetPlayerFromIdentifier(inventoryId)
    -- if xPlayer then
    --     local playerId = xPlayer.source
    --     print(string.format("Player %d removed item %s", playerId, itemName))
    -- end
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string | L'identifiant de l'inventaire. Pour les joueurs, c'est l'identifiant du personnage |
| `itemName` | string | Le nom de l'item retiré |
| `amount` | number | La quantité retirée |
| `metadata` | table | Les métadonnées de l'item |
| `slotId` | number \| nil | Le slot depuis lequel l'item a été retiré (peut être nil si aucun slot n'était spécifié lors du retrait) |
