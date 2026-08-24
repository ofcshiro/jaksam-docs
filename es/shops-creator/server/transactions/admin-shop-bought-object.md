---
title: "Objeto comprado en tienda de admin"
description: "Se activa cuando un jugador compra un objeto en una tienda de administrador."
icon: "hand-holding-dollar"
---

Se activa después de que un jugador compra un objeto en una tienda de administrador.

```lua Event
RegisterNetEvent("shops_creator:adminShops:boughtObject", function(playerId, shopId, itemId, quantity, totalPrice)

end)
```

### Parámetros

| Nombre         | Tipo de dato | Descripción                                     |
| ------------ | --------- | -------------------------------------------------- |
| `playerId`   | integer   | El ID del jugador que compró el objeto                 |
| `shopId`     | integer   | El ID de la tienda (el mismo que está en la base de datos)   |
| `itemId`     | string    | El ID del item comprado                          |
| `quantity`   | integer   | La cantidad de items comprados                          |
| `totalPrice` | integer   | El precio total de los items comprados                   |

<Note>
  Coloca este código en el archivo `integrations/sv_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
