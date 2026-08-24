---
title: "Objet vendu dans une boutique admin"
description: "Se déclenche quand un joueur vend un objet à une boutique d'administrateur."
icon: "hand-holding-dollar"
---

Se déclenche après qu'un joueur vend un objet à une boutique d'administrateur.

```lua Event
RegisterNetEvent("shops_creator:adminShops:soldObject", function(playerId, shopId, itemId, quantity, totalPrice)

end)
```

### Paramètres

| Nom         | Type de donnée | Description                                     |
| ------------ | --------- | -------------------------------------------------- |
| `playerId`   | integer   | L'ID du joueur qui a vendu l'objet                    |
| `shopId`     | integer   | L'ID de la boutique (le même que celui de la base de données)   |
| `itemId`     | string    | L'ID de l'item vendu                             |
| `quantity`   | integer   | La quantité d'items vendus                             |
| `totalPrice` | integer   | Le prix total des items vendus                      |

<Note>
  Place ce code dans le fichier `integrations/sv_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
