---
title: "Bypass start vehicle check"
description: "Contourne les conditions de démarrage du véhicule à l'aide d'un state bag."
icon: "key"
---

Tu peux contourner la vérification de démarrage du véhicule en définissant le state bag `canAlwaysStart` sur `true`.

## Exemple

```lua
-- Cette commande permet au joueur de contourner les conditions de démarrage du véhicule actuel
RegisterCommand("startbypass", function()
    local plyPed = PlayerPedId()
    local plyVeh = GetVehiclePedIsIn(plyPed)

    Entity(plyVeh).state.canAlwaysStart = true
end)
```

<Note>
  Le contournement s'applique lorsque tu entres dans le véhicule **après** son activation.
</Note>
