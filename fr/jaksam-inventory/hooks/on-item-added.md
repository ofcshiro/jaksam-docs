---
title: "Item added"
description: "Hook déclenché quand un item est ajouté à un inventaire."
icon: "circle-plus"
---

Se déclenche quand un item est ajouté à un inventaire. Enregistre-le avec [`registerHook`](/fr/jaksam-inventory/hooks#register-a-hook) en utilisant le nom d'event `onItemAdded`.

### Payload

| Champ | Type de donnée | Description |
| --- | --- | --- |
| `inventoryId` | string | par exemple `"player:1"` |
| `itemName` | string | par exemple `"bread"` |
| `amount` | number | Quantité ajoutée |
| `metadata` | table \| nil | Métadonnées de l'item, peut être nil |
| `slotId` | number | Slot où l'item a été ajouté |

### Exemples

<AccordionGroup>
  <Accordion title="Un seul sac à dos par joueur">
    ```lua
    exports['jaksam_inventory']:registerHook("onItemAdded", function(payload)
        local backpackCount = exports["jaksam_inventory"]:getTotalItemAmount(payload.inventoryId, "backpack")
        if backpackCount >= 1 then
            return false, "You can only have one backpack"
        end
    end, {
        itemNameFilter = {backpack = true},
        inventoryTypeFilter = {player = true}
    })
    ```
  </Accordion>

  <Accordion title="Filtrer par nom d'inventaire spécifique">
    ```lua
    -- Ne se déclenche que quand des items sont ajoutés à la planque de police
    exports['jaksam_inventory']:registerHook("onItemAdded", function(payload)
        print("Item added to police stash:", payload.itemName)
    end, {
        inventoryFilter = {"stash_police"}
    })
    ```
  </Accordion>
</AccordionGroup>

Voir [l'aperçu des Hooks](/fr/jaksam-inventory/hooks) pour l'API `registerHook`, les filtres disponibles, et le comportement des valeurs de retour.
