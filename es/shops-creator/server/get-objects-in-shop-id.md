---
title: "Obtener objetos en el ID de tienda"
description: "Obtén qué objetos se están vendiendo o comprando en una tienda determinada."
icon: "boxes-stacked"
---

Este export devuelve qué objetos se están vendiendo/comprando en un ID de tienda.

```lua Export
local objectsInShop = getAllObjectFromPlayersShopId(shopId)
```

### Parámetros

| Nombre     | Tipo de dato | Descripción                                     |
| -------- | --------- | -------------------------------------------------- |
| `shopId` | integer   | El ID de la tienda (el mismo que está en la base de datos)   |

### Ejemplo de salida

```lua
{
	[64] = {
		["name"] = "beer",
		["price"] = 5,
		["type"] = "item",
		["quantity"] = 1,
		["label"] = "Beer",
		["method"] = "buy", -- El jugador puede comprar el item
		["id"] = 64,
	},
	[65] = {
		["name"] = "weed_seed",
		["price"] = 555,
		["type"] = "item",
		["quantity"] = 5,
		["label"] = "Weed Seed",
		["method"] = "sell",  -- El jugador puede vender el item
		["id"] = 65,
	},
	[63] = {
		["name"] = "accesscard",
		["price"] = 5,
		["type"] = "item",
		["quantity"] = 1,
		["label"] = "Access Card",
		["method"] = "buy", -- El jugador puede comprar el item
		["id"] = 63,
	},
}
```

<Note>
  Coloca este código en el archivo `integrations/sv_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
