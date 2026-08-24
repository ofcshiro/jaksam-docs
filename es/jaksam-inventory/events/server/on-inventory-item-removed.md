---
title: "Inventory item removed"
description: "Se activa cuando un ítem se elimina correctamente de un inventario."
icon: "circle-minus"
---

Se activa cuando un ítem se elimina correctamente de un inventario.

<CodeGroup>

```lua Event
AddEventHandler('jaksam_inventory:onInventoryItemRemoved', function(inventoryId, itemName, amount, metadata, slotId)
end)
```

```lua Example
AddEventHandler('jaksam_inventory:onInventoryItemRemoved', function(inventoryId, itemName, amount, metadata, slotId)
    local inventoryType = exports['jaksam_inventory']:getInventoryType(inventoryId)
    if inventoryType ~= 'player' then return end -- Solo manejar inventarios de jugador

    print(string.format("Item %s (x%d) removed from inventory %s", itemName, amount, inventoryId))

    -- Para QBCore: Obtener jugador por identificador de personaje
    local Player = exports['qb-core']:GetPlayerByCitizenId(inventoryId)
    if Player then
        local playerId = Player.PlayerData.source
        print(string.format("Player %d removed item %s", playerId, itemName))

        -- Ejemplo: Registrar en Discord o en la base de datos
        -- exports['your_logs']:log({
        --     event = "item_removed",
        --     playerId = playerId,
        --     item = itemName,
        --     amount = amount
        -- })
    end

    -- Para ESX: Obtener jugador por identificador de personaje
    -- local xPlayer = ESX.GetPlayerFromIdentifier(inventoryId)
    -- if xPlayer then
    --     local playerId = xPlayer.source
    --     print(string.format("Player %d removed item %s", playerId, itemName))
    -- end
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de Dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string | El identificador del inventario. Para jugadores, es el identificador del personaje |
| `itemName` | string | El nombre del ítem eliminado |
| `amount` | number | La cantidad eliminada |
| `metadata` | table | Los metadatos del ítem |
| `slotId` | number \| nil | El slot del que se eliminó el ítem (puede ser nil si no se especificó un slot al eliminar el ítem) |
