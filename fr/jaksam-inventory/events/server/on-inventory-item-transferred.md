---
title: "Inventory item transferred"
description: "Se déclenche quand un item est transféré avec succès d'un inventaire à un autre."
icon: "right-left"
---

Se déclenche quand un item est transféré avec succès d'un inventaire à un autre (y compris les déplacements intra-inventaire).

<CodeGroup>

```lua Event
AddEventHandler('jaksam_inventory:onInventoryItemTransferred', function(inventoryIdFrom, inventoryIdTo, itemName, amount, metadata, slotIdFrom, slotIdTo)
end)
```

```lua Example
AddEventHandler('jaksam_inventory:onInventoryItemTransferred', function(inventoryIdFrom, inventoryIdTo, itemName, amount, metadata, slotIdFrom, slotIdTo)
    local inventoryTypeFrom = exports['jaksam_inventory']:getInventoryType(inventoryIdFrom)
    local inventoryTypeTo = exports['jaksam_inventory']:getInventoryType(inventoryIdTo)
    if inventoryTypeFrom ~= 'player' or inventoryTypeTo ~= 'player' then return end -- Ne gère que les inventaires de joueur

    print(string.format("Item %s (x%d) transferred from %s to %s", itemName, amount, inventoryIdFrom, inventoryIdTo))

    -- Pour QBCore
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

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryIdFrom` | string | L'identifiant de l'inventaire source. Pour les joueurs, c'est l'identifiant du personnage |
| `inventoryIdTo` | string | L'identifiant de l'inventaire de destination. Pour les joueurs, c'est l'identifiant du personnage |
| `itemName` | string | Le nom de l'item transféré |
| `amount` | number | La quantité transférée |
| `metadata` | table | Les métadonnées de l'item |
| `slotIdFrom` | number \| nil | Le slot depuis lequel l'item a été transféré |
| `slotIdTo` | number \| nil | Le slot vers lequel l'item a été transféré |

<Warning>
  Le contenu source signalait un vrai bug Lua dans l'exemple d'origine (blocs `end` déséquilibrés et une variable non définie), corrigé lors d'une passe précédente pour donner le code fonctionnel ci-dessus, en suivant le même modèle QBCore que les autres events. À vérifier que ça correspond bien à ta propre logique.
</Warning>
