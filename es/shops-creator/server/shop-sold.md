---
title: "Tienda vendida"
description: "Se activa cuando un jugador vende una tienda propiedad de otro jugador."
icon: "hand-holding-dollar"
---

Se activa después de que un jugador vende una tienda propiedad de otro jugador.

```lua Event
RegisterNetEvent("shops_creator:playersShops:shopSold", function(shopId, ownerIdentifier)

end)
```

### Parámetros

| Nombre         | Tipo de dato | Descripción                                     |
| ------------ | --------- | -------------------------------------------------- |
| `shopId`     | integer   | El ID de la tienda (el mismo que está en la base de datos)   |
| `identifier` | string    | El identifier del anterior propietario                     |

<Note>
  Coloca este código en el archivo `integrations/sv_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
