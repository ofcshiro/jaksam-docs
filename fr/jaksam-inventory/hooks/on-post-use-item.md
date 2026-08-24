---
title: "Post use item"
description: "Hook déclenché après qu'un item ait été utilisé, notification uniquement."
icon: "circle-check"
---

Se déclenche APRÈS qu'un item ait été utilisé (après la consommation, les animations, les délais et tous les callbacks). Enregistre-le avec [`registerHook`](/fr/jaksam-inventory/hooks#register-a-hook) en utilisant le nom d'event `onPostUseItem`.

**Ordre d'exécution :** tout à la fin du processus d'utilisation de l'item, après `oxServerExport 'usedItem'`.

### Payload

| Champ | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | number | Le joueur qui a utilisé l'item |
| `inventoryId` | string | par exemple `"license:abcd1234"` |
| `slotId` | number | Slot de l'item qui a été utilisé |
| `itemName` | string | par exemple `"bread"` |
| `metadata` | table \| nil | Métadonnées de l'item |

<Note>
  Ce hook est uniquement une notification et ne peut pas annuler l'utilisation de l'item. Utile pour les logs, statistiques, succès, et pour déclencher des systèmes externes.
</Note>

### Exemples

<AccordionGroup>
  <Accordion title="Enregistrer toute utilisation d'items">
    ```lua
    exports['jaksam_inventory']:registerHook("onPostUseItem", function(payload)
        print(("Player %d used %s"):format(payload.playerId, payload.itemName))
        -- Envoie vers un système de logs externe, une base de données, etc.
    end)
    ```
  </Accordion>

  <Accordion title="Suivre les statistiques de consommation de nourriture">
    ```lua
    local foodStats = {}

    exports['jaksam_inventory']:registerHook("onPostUseItem", function(payload)
        foodStats[payload.itemName] = (foodStats[payload.itemName] or 0) + 1
        print("Total", payload.itemName, "consumed:", foodStats[payload.itemName])
    end, {
        itemTypeFilter = {food = true}
    })
    ```
  </Accordion>
</AccordionGroup>

Voir [l'aperçu des Hooks](/fr/jaksam-inventory/hooks) pour l'API `registerHook`, les filtres disponibles, et le comportement des valeurs de retour.
