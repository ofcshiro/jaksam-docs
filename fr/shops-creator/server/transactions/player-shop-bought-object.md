---
title: "Objet acheté dans une boutique de joueur"
description: "Se déclenche quand un joueur achète un objet dans une boutique appartenant à un autre joueur."
icon: "hand-holding-dollar"
---

Se déclenche après qu'un joueur achète un objet dans une boutique appartenant à un autre joueur.

```lua Event
RegisterNetEvent("shops_creator:playersShops:boughtObject", function(playerId, shopId, objectId, quantity, totalPrice)

end)
```

### Paramètres

| Nom         | Type de donnée | Description                                     |
| ------------ | --------- | -------------------------------------------------- |
| `playerId`   | integer   | L'ID du joueur qui a acheté l'objet                 |
| `shopId`     | integer   | L'ID de la boutique (le même que celui de la base de données)   |
| `objectId`   | integer   | L'ID de l'objet acheté                         |
| `quantity`   | integer   | La quantité d'items achetés                          |
| `totalPrice` | integer   | Le prix total des items achetés                   |

<Note>
  Place ce code dans le fichier `integrations/sv_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
