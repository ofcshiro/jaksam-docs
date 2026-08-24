---
title: "Objeto vendido en tienda de admin"
description: "Se activa cuando un jugador vende un objeto a una tienda de administrador."
icon: "hand-holding-dollar"
---

Se activa después de que un jugador vende un objeto a una tienda de administrador.

```lua Event
RegisterNetEvent("shops_creator:adminShops:soldObject", function(playerId, shopId, itemId, quantity, totalPrice)

end)
```

### Parámetros

| Nombre         | Tipo de dato | Descripción                                     |
| ------------ | --------- | -------------------------------------------------- |
| `playerId`   | integer   | El ID del jugador que vendió el objeto                    |
| `shopId`     | integer   | El ID de la tienda (el mismo que está en la base de datos)   |
| `itemId`     | string    | El ID del item vendido                             |
| `quantity`   | integer   | La cantidad de items vendidos                             |
| `totalPrice` | integer   | El precio total de los items vendidos                      |

<Note>
  Coloca este código en el archivo `integrations/sv_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
