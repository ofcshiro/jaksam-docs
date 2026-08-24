---
title: "Get item from slot"
description: "Récupère un objet depuis un emplacement spécifique d'un inventaire."
icon: "grid-2"
---

Récupère un objet depuis un emplacement spécifique d'un inventaire.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemFromSlot(inventoryId, slotId, returnRaw)
```

```lua Example
-- Récupère l'objet de l'emplacement 5 du joueur
local playerId = 1
local item = exports['jaksam_inventory']:getItemFromSlot(playerId, 5)

if item then
    print('Item name:', item.name)
    print('Amount:', item.amount)
    print('Metadata:', json.encode(item.metadata))

    item.metadata.durability = 50 -- met à jour les métadonnées
    exports['jaksam_inventory']:setItemMetadataInSlot(playerId, 5, item.metadata) -- sauvegarde les métadonnées
end

-- Récupère un objet depuis une stash
local stashItem = exports['jaksam_inventory']:getItemFromSlot('police_stash_1', 3)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| number | L'ID de l'inventaire depuis lequel récupérer l'objet. Peut être l'ID serveur d'un joueur (number) ou un ID d'inventaire (string) |
| `slotId` | number | Le numéro de l'emplacement depuis lequel récupérer l'objet |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `item` | table \| nil | L'objet dans l'emplacement (`name`, `amount`, `metadata`), ou nil si l'emplacement est vide |

### Notes

<Info>
  [TODO: INFORMATION NEEDED] La signature de l'export accepte un troisième paramètre `returnRaw` qui n'est pas documenté dans le matériel source utilisé pour cette page.
</Info>
