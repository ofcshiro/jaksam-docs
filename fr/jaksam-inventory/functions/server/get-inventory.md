---
title: "Get inventory"
description: "Récupère les données complètes d'un inventaire, y compris ses objets, ses limites de poids et ses métadonnées."
icon: "boxes-stacked"
---

Récupère les données complètes d'un inventaire, y compris ses objets, ses limites de poids et ses métadonnées.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getInventory(inventoryId)
```

```lua Example
-- Récupère l'inventaire d'un joueur
local inventory = exports['jaksam_inventory']:getInventory(1) -- joueur avec l'ID serveur 1

-- Récupère l'inventaire d'une stash
local stashInv = exports['jaksam_inventory']:getInventory('police_stash_1')

if inventory then
    print(inventory.totalWeight) -- affiche le poids actuel
    print(inventory.limits.maxWeight) -- affiche le poids maximum autorisé
    print(json.encode(inventory.items, {indent = true})) -- {["SLOT-4"] = {name = "itemName", amount = 1, metadata = {}}}
end
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string \| number | L'ID de l'inventaire dont récupérer les données. Peut être l'ID serveur d'un joueur (number) ou un ID d'inventaire (string) |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventory` | table \| nil | `{id, label, type, options, items, totalWeight, limits: {maxSlots, maxWeight}, metadata}` |
