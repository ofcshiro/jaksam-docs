---
title: "Get item from slot"
description: "Récupère un item depuis un slot spécifique de l'inventaire du joueur."
icon: "grid-2"
---

Récupère un item depuis un slot spécifique de l'inventaire du joueur.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemFromSlot(slotId)
```

```lua Example
-- Récupère l'item du slot 5 du joueur
local item = exports['jaksam_inventory']:getItemFromSlot(5)

if item then
    print('Item name:', item.name)
    print('Amount:', item.amount)
    if item.metadata then
        print('Metadata:', json.encode(item.metadata))
    end
else
    print('Slot 5 is empty')
end

-- Vérifie si un slot spécifique contient une arme
local slotItem = exports['jaksam_inventory']:getItemFromSlot(1)
if slotItem then
  local staticItem = exports['jaksam_inventory']:getStaticItem(slotItem.name)
  if staticItem and staticItem.type == 'weapon' then
    print('Found weapon in slot 1:', slotItem.name)
  end
end
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `slotId` | number | Le numéro du slot depuis lequel récupérer l'item (dans l'inventaire du joueur) |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `item` | table \| nil | L'item dans le slot (`name`, `amount`, `metadata`), ou nil si le slot est vide |
