---
title: "Obtenir les objets d'un ID de boutique"
description: "Récupère quels objets sont vendus ou achetés dans une boutique donnée."
icon: "boxes-stacked"
---

Cet export retourne quels objets sont vendus/achetés dans un ID de boutique.

```lua Export
local objectsInShop = getAllObjectFromPlayersShopId(shopId)
```

### Paramètres

| Nom     | Type de donnée | Description                                     |
| -------- | --------- | -------------------------------------------------- |
| `shopId` | integer   | L'ID de la boutique (le même que celui de la base de données)   |

### Exemple de sortie

```lua
{
	[64] = {
		["name"] = "beer",
		["price"] = 5,
		["type"] = "item",
		["quantity"] = 1,
		["label"] = "Beer",
		["method"] = "buy", -- Le joueur peut acheter l'item
		["id"] = 64,
	},
	[65] = {
		["name"] = "weed_seed",
		["price"] = 555,
		["type"] = "item",
		["quantity"] = 5,
		["label"] = "Weed Seed",
		["method"] = "sell",  -- Le joueur peut vendre l'item
		["id"] = 65,
	},
	[63] = {
		["name"] = "accesscard",
		["price"] = 5,
		["type"] = "item",
		["quantity"] = 1,
		["label"] = "Access Card",
		["method"] = "buy", -- Le joueur peut acheter l'item
		["id"] = 63,
	},
}
```

<Note>
  Place ce code dans le fichier `integrations/sv_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
