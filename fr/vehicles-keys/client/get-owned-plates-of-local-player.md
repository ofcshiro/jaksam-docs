---
title: "Get owned plates of local player"
description: "Récupère toutes les plaques de véhicule possédées par le joueur local."
icon: "list"
---

Cet export récupère toutes les plaques possédées par **le joueur local**.

```lua Export
local ownedPlates = exports["vehicles_keys"]:getOwnedVehiclePlates()
```

### Valeur de retour

Une table contenant toutes les plaques possédées, avec le format suivant :

```lua
{
    ["ABC123"] = {
        type = "owned",
        model = -35726841
    },

    ["BCD473"] = {
        type = "temporary",
        model = -55726841
    },
}
```
