---
title: "Obtener qué objetos se pueden vender en el ID de tienda"
description: "Obtén qué objetos puede vender un jugador en una tienda, según su configuración de whitelist/blacklist."
icon: "tags"
---

Este export devuelve qué objetos puede vender el jugador en el ID de tienda, según la whitelist/blacklist de la tienda y si la tienda tiene permitido gestionar armas y/o items.

```lua Export
local sellableObjects = getSellableObjectsForShopId(playerId, shopId)
```

### Parámetros

| Nombre       | Tipo de dato | Descripción                                     |
| ---------- | --------- | -------------------------------------------------- |
| `playerId` | integer   | El server ID del jugador                                |
| `shopId`   | integer   | El ID de la tienda (el mismo que está en la base de datos)   |

### Ejemplo de salida

```lua
{
	[1] = {
	        ["name"] = "accesscard",
	        ["count"] = 14,
	        ["label"] = "Access Card",
	        ["type"] = "item",
        },
	[2] = {
		["name"] = "bag",
		["count"] = 49,
		["label"] = "Bag",
		["type"] = "item",
	},
	[3] = {
		["name"] = "WEAPON_COMPACTLAUNCHER",
		["count"] = 1,
		["label"] = "Compact launcher",
		["type"] = "weapon",
	},
	[4] = {
		["name"] = "WEAPON_MACHINEPISTOL",
		["count"] = 1,
		["label"] = "Machine pistol",
		["type"] = "weapon",
	}
}
```

<Note>
  Coloca este código en el archivo `integrations/sv_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
