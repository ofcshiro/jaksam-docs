---
title: "Pocket crafting finished"
description: "Déclenché côté serveur quand un joueur termine un processus de pocket crafting."
icon: "flask-vial"
---

Cet event est déclenché après qu'un joueur ait terminé avec succès un processus de pocket crafting. Il est envoyé juste après que le joueur reçoive l'item crafté.

```lua Event
AddEventHandler("drugs_creator:pocketCraftingFinished", function(playerId, itemName)

end)
```

### Paramètres

| Nom        | Type de donnée | Description                                                  |
| ----------- | --------- | ------------------------------------------------------------- |
| `playerId`  | integer   | L'ID serveur du joueur qui a terminé le craft            |
| `itemName`  | string    | Le nom de l'item de pocket crafting utilisé                 |

## Exemple

```lua
AddEventHandler("drugs_creator:pocketCraftingFinished", function(playerId, itemName)
    print("Player " .. playerId .. " finished crafting with " .. itemName)
end)
```
