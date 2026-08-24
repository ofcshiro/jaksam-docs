---
title: "Inventory item transferred"
description: "Se activa cuando un ítem se transfiere correctamente de un inventario a otro."
icon: "right-left"
---

Se activa cuando un ítem se transfiere correctamente de un inventario a otro (incluyendo movimientos dentro del mismo inventario).

<CodeGroup>

```lua Event
AddEventHandler('jaksam_inventory:onInventoryItemTransferred', function(inventoryIdFrom, inventoryIdTo, itemName, amount, metadata, slotIdFrom, slotIdTo)
end)
```

```lua Example
AddEventHandler('jaksam_inventory:onInventoryItemTransferred', function(inventoryIdFrom, inventoryIdTo, itemName, amount, metadata, slotIdFrom, slotIdTo)
    local inventoryTypeFrom = exports['jaksam_inventory']:getInventoryType(inventoryIdFrom)
    local inventoryTypeTo = exports['jaksam_inventory']:getInventoryType(inventoryIdTo)
    if inventoryTypeFrom ~= 'player' or inventoryTypeTo ~= 'player' then return end -- Solo manejar inventarios de jugador

    print(string.format("Item %s (x%d) transferred from %s to %s", itemName, amount, inventoryIdFrom, inventoryIdTo))

    -- Para QBCore
    local PlayerFrom = exports['qb-core']:GetPlayerByCitizenId(inventoryIdFrom)
    local PlayerTo = exports['qb-core']:GetPlayerByCitizenId(inventoryIdTo)

    if PlayerFrom and PlayerTo then
        local playerIdFrom = PlayerFrom.PlayerData.source
        local playerIdTo = PlayerTo.PlayerData.source
        print(string.format("Player %d transferred item %s (x%d) to player %d", playerIdFrom, itemName, amount, playerIdTo))
    end
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de Dato | Descripción |
| --- | --- | --- |
| `inventoryIdFrom` | string | El identificador del inventario de origen. Para jugadores, es el identificador del personaje |
| `inventoryIdTo` | string | El identificador del inventario de destino. Para jugadores, es el identificador del personaje |
| `itemName` | string | El nombre del ítem transferido |
| `amount` | number | La cantidad transferida |
| `metadata` | table | Los metadatos del ítem |
| `slotIdFrom` | number \| nil | El slot desde el cual se transfirió el ítem |
| `slotIdTo` | number \| nil | El slot al cual se transfirió el ítem |

<Warning>
  La documentación original señalaba un bug real de Lua en el ejemplo original (bloques `end` desbalanceados y una variable no definida) que una revisión anterior corrigió al código funcional mostrado arriba, siguiendo el mismo patrón de QBCore que los demás events. Vale la pena verificar que coincida con tu lógica real.
</Warning>
