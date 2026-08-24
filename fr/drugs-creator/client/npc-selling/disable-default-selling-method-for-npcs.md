---
title: "Disable default selling method for NPCs"
description: "Désactive le message par défaut 'Press E to sell drugs' au-dessus des PNJ."
icon: "ban"
---

Event pour désactiver le message au-dessus des PNJ, `Press E to sell drugs`.

<Note>
  Si tu désactives ce message, tu dois déclencher manuellement l'event `drugs_creator:sellToNPC` pour vendre aux PNJ.
</Note>

```lua Event
TriggerEvent("drugs_creator:disableDefaultSellingMethodNPC")
```

## Exemple

```lua
-- Désactive le message
RegisterNetEvent("drugs_creator:framework:ready", function()
    TriggerEvent("drugs_creator:disableDefaultSellingMethodNPC")
end)

-- Vend manuellement à un NPC (exemple pour les scripts de targeting)
Citizen.CreateThread(function()
    local closestPed = ESX.Game.GetClosestPed()

    TriggerEvent("drugs_creator:sellToNPC", closestPed)
end)
```
