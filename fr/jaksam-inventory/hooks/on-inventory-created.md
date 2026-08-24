---
title: "Inventory created"
description: "Hook déclenché quand un nouvel inventaire est créé, notification uniquement."
icon: "wand-magic-sparkles"
---

Se déclenche quand un nouvel inventaire est créé. Enregistre-le avec [`registerHook`](/fr/jaksam-inventory/hooks#register-a-hook) en utilisant le nom d'event `onInventoryCreated`.

### Payload

| Champ | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string | par exemple `"stash_police"` |
| `inventoryType` | string | par exemple `"stash"` |
| `label` | string | par exemple `"Police Stash"` |
| `options` | table \| nil | Peut être nil si non défini explicitement, auquel cas ça suit la config des options globales d'inventaire |
| `items` | table | Items présents dans l'inventaire à sa création |
| `metadata` | table | Métadonnées additionnelles de l'inventaire |

<Note>
  Ce hook est uniquement une notification et ne peut pas annuler la création de l'inventaire. Utile pour ajouter des items de départ, pré-remplir des inventaires avec du loot aléatoire, ou enregistrer la création d'inventaires. Utilise les exports pour ajouter des items à l'inventaire dans le callback.
</Note>

**Filtres disponibles :** `inventoryTypeFilter` (filtre par type d'inventaire : player, stash, trunk, dumpster, etc.), `inventoryFilter` (filtre par motifs d'ID d'inventaire spécifiques).

### Exemples

<AccordionGroup>
  <Accordion title="Ajouter des items de départ aux nouveaux inventaires de joueur">
    ```lua
    exports['jaksam_inventory']:registerHook("onInventoryCreated", function(payload)
        exports["jaksam_inventory"]:addItem(payload.inventoryId, "bread", 5)
        exports["jaksam_inventory"]:addItem(payload.inventoryId, "water", 3)
        exports["jaksam_inventory"]:addItem(payload.inventoryId, "phone", 1)
    end, {
        inventoryTypeFilter = {player = true}
    })
    ```
  </Accordion>

  <Accordion title="Remplir les poubelles avec du loot aléatoire">
    <Note>
      Un hook existant pour ça est déjà fourni dans le dossier `_hooks` de jaksam_inventory.
    </Note>

    ```lua
    -- Table de loot : chaque entrée a itemName, minAmount, maxAmount
    local lootTable = {
        {name = "trash", min = 1, max = 5},
        {name = "newspaper", min = 1, max = 2},
        {name = "bottle", min = 1, max = 3},
        {name = "sandwich", min = 1, max = 1},
        {name = "bandage", min = 1, max = 2},
    }

    -- Nombre min et max d'items différents par poubelle
    local minItems, maxItems = 1, 3

    -- Mélange Fisher-Yates pour une sélection aléatoire sans répétition
    local function shuffleTable(tbl)
        local shuffled = {}
        for i = 1, #tbl do shuffled[i] = tbl[i] end
        for i = #shuffled, 2, -1 do
            local j = math.random(1, i)
            shuffled[i], shuffled[j] = shuffled[j], shuffled[i]
        end
        return shuffled
    end

    exports['jaksam_inventory']:registerHook("onInventoryCreated", function(payload)
        local itemCount = math.random(minItems, math.min(maxItems, #lootTable))
        local shuffledLoot = shuffleTable(lootTable)

        for i = 1, itemCount do
            local loot = shuffledLoot[i]
            local amount = math.random(loot.min, loot.max)
            exports["jaksam_inventory"]:addItem(payload.inventoryId, loot.name, amount)
        end
    end, {
        inventoryTypeFilter = {dumpster = true}
    })
    ```
  </Accordion>
</AccordionGroup>

Voir [l'aperçu des Hooks](/fr/jaksam-inventory/hooks) pour l'API `registerHook`, les filtres disponibles, et le comportement des valeurs de retour.
