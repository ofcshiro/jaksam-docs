---
title: "Boutique achetée"
description: "Se déclenche quand un joueur achète une boutique appartenant à un autre joueur."
icon: "hand-holding-dollar"
---

Se déclenche après qu'un joueur achète une boutique appartenant à un autre joueur.

```lua Event
RegisterNetEvent("shops_creator:playersShops:shopBought", function(shopId, ownerIdentifier)

end)
```

### Paramètres

| Nom         | Type de donnée | Description                                     |
| ------------ | --------- | -------------------------------------------------- |
| `shopId`     | integer   | L'ID de la boutique (le même que celui de la base de données)   |
| `identifier` | string    | L'identifier du nouveau propriétaire                     |

<Note>
  Place ce code dans le fichier `integrations/sv_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
