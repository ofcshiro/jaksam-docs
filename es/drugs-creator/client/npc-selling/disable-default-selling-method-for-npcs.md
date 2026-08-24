---
title: "Disable default selling method for NPCs"
description: "Desactiva el aviso por defecto 'Press E to sell drugs' sobre los NPCs."
icon: "ban"
---

Event para desactivar el aviso sobre los NPCs, `Press E to sell drugs`.

<Note>
  Si desactivas el aviso, tendrás que activar manualmente el event `drugs_creator:sellToNPC` para vender a los NPCs.
</Note>

```lua Event
TriggerEvent("drugs_creator:disableDefaultSellingMethodNPC")
```

## Ejemplo

```lua
-- Desactiva el aviso
RegisterNetEvent("drugs_creator:framework:ready", function()
    TriggerEvent("drugs_creator:disableDefaultSellingMethodNPC")
end)

-- Vender manualmente a un NPC (ejemplo para scripts de targeting)
Citizen.CreateThread(function()
    local closestPed = ESX.Game.GetClosestPed()

    TriggerEvent("drugs_creator:sellToNPC", closestPed)
end)
```
