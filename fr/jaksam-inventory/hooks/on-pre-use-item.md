---
title: "Pre use item"
description: "Hook déclenché avant qu'un item soit utilisé, peut annuler l'utilisation."
icon: "hand"
---

Se déclenche AVANT qu'un item soit utilisé (avant la consommation, les animations et les délais). Ce hook peut annuler l'utilisation de l'item. Enregistre-le avec [`registerHook`](/fr/jaksam-inventory/hooks#enregistrer-un-hook) en utilisant le nom d'event `onPreUseItem`.

**Ordre d'exécution :** après `STATIC_ITEM.canUse` et `oxServerExport 'usingItem'`, avant la consommation.

### Payload

| Champ | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | number | Le joueur utilisant l'item |
| `inventoryId` | string | par exemple `"license:abcd1234"` |
| `slotId` | number | Slot de l'item utilisé |
| `itemName` | string | par exemple `"bread"` |
| `metadata` | table \| nil | Métadonnées de l'item |

<Note>
  Ce hook peut empêcher l'utilisation de l'item en retournant `false`. Utile pour des restrictions globales d'utilisation d'items (par exemple, joueurs menottés, restrictions en véhicule, restrictions de zone).
</Note>

### Exemples

<AccordionGroup>
  <Accordion title="Bloquer l'utilisation d'items quand menotté">
    ```lua
    exports['jaksam_inventory']:registerHook("onPreUseItem", function(payload)
        if IsPlayerHandcuffed(payload.playerId) then
            return false, "You cannot use items while handcuffed"
        end
    end)
    ```
  </Accordion>

  <Accordion title="Bloquer l'utilisation de nourriture en véhicule">
    ```lua
    exports['jaksam_inventory']:registerHook("onPreUseItem", function(payload)
        local ped = GetPlayerPed(payload.playerId)
        if IsPedInAnyVehicle(ped, false) then
            return false, "You cannot eat while driving", "warning"
        end
    end, {
        itemTypeFilter = {food = true}
    })
    ```
  </Accordion>
</AccordionGroup>

Voir [l'aperçu des Hooks](/fr/jaksam-inventory/hooks) pour l'API `registerHook`, les filtres disponibles, et le comportement des valeurs de retour.
