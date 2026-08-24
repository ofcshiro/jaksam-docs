---
title: "Inventory item added"
description: "Se activa cuando un ítem se agrega correctamente a un inventario."
icon: "circle-plus"
---

Se activa cuando un ítem se agrega correctamente a un inventario.

<CodeGroup>

```lua Event
AddEventHandler('jaksam_inventory:onInventoryItemAdded', function(inventoryId, itemName, amount, metadata, slotId)
end)
```

```lua Example
AddEventHandler('jaksam_inventory:onInventoryItemAdded', function(inventoryId, itemName, amount, metadata, slotId)
    local inventoryType = exports['jaksam_inventory']:getInventoryType(inventoryId)
    if inventoryType ~= 'player' then return end -- Solo manejar inventarios de jugador

    print(string.format("Item %s (x%d) added to inventory %s", itemName, amount, inventoryId))

    -- Para QBCore: Obtener jugador por identificador de personaje
    local Player = exports['qb-core']:GetPlayerByCitizenId(inventoryId)
    if Player then
        local playerId = Player.PlayerData.source
        print(string.format("Player %d added item %s", playerId, itemName))
    end

    -- Para ESX: Obtener jugador por identificador de personaje
    -- local xPlayer = ESX.GetPlayerFromIdentifier(inventoryId)
    -- if xPlayer then
    --     local playerId = xPlayer.source
    --     print(string.format("Player %d added item %s", playerId, itemName))
    -- end
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de Dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string | El identificador del inventario. Para jugadores, es el identificador del personaje |
| `itemName` | string | El nombre del ítem agregado |
| `amount` | number | La cantidad agregada |
| `metadata` | table | Los metadatos del ítem |
| `slotId` | number \| nil | El slot donde se agregó el ítem (puede ser nil si no se especificó un slot al agregar el ítem) |
