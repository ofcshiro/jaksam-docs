---
title: "Objet acheté dans une boutique admin"
description: "Se déclenche quand un joueur achète un objet dans une boutique d'administrateur."
icon: "hand-holding-dollar"
---

Se déclenche après qu'un joueur achète un objet dans une boutique d'administrateur.

```lua Event
RegisterNetEvent("shops_creator:adminShops:boughtObject", function(playerId, shopId, itemId, quantity, totalPrice)

end)
```

### Paramètres

| Nom         | Type de donnée | Description                                     |
| ------------ | --------- | -------------------------------------------------- |
| `playerId`   | integer   | L'ID du joueur qui a acheté l'objet                 |
| `shopId`     | integer   | L'ID de la boutique (le même que celui de la base de données)   |
| `itemId`     | string    | L'ID de l'item acheté                          |
| `quantity`   | integer   | La quantité d'items achetés                          |
| `totalPrice` | integer   | Le prix total des items achetés                   |

<Note>
  Place ce code dans le fichier `integrations/sv_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
