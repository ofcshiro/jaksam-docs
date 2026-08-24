---
title: "Obtenir les objets vendables dans un ID de boutique"
description: "Récupère quels objets un joueur peut vendre dans une boutique, selon sa configuration whitelist/blacklist."
icon: "tags"
---

Cet export retourne quels objets le joueur peut vendre dans l'ID de boutique, selon la whitelist/blacklist de la boutique et selon si la boutique est autorisée à gérer des armes et/ou des items.

```lua Export
local sellableObjects = getSellableObjectsForShopId(playerId, shopId)
```

### Paramètres

| Nom       | Type de donnée | Description                                     |
| ---------- | --------- | -------------------------------------------------- |
| `playerId` | integer   | Le server ID du joueur                                |
| `shopId`   | integer   | L'ID de la boutique (le même que celui de la base de données)   |

### Exemple de sortie

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
  Place ce code dans le fichier `integrations/sv_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
