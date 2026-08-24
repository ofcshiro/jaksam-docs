---
title: "Objeto comprado en tienda de jugador"
description: "Se activa cuando un jugador compra un objeto en una tienda propiedad de otro jugador."
icon: "hand-holding-dollar"
---

Se activa después de que un jugador compra un objeto en una tienda propiedad de otro jugador.

```lua Event
RegisterNetEvent("shops_creator:playersShops:boughtObject", function(playerId, shopId, objectId, quantity, totalPrice)

end)
```

### Parámetros

| Nombre         | Tipo de dato | Descripción                                     |
| ------------ | --------- | -------------------------------------------------- |
| `playerId`   | integer   | El ID del jugador que compró el objeto                 |
| `shopId`     | integer   | El ID de la tienda (el mismo que está en la base de datos)   |
| `objectId`   | integer   | El ID del objeto comprado                         |
| `quantity`   | integer   | La cantidad de items comprados                          |
| `totalPrice` | integer   | El precio total de los items comprados                   |

<Note>
  Coloca este código en el archivo `integrations/sv_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
