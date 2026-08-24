---
title: "Replace default notifications"
description: "Utilise un système de notification personnalisé à la place de celui par défaut en écoutant l'event notify."
icon: "bell"
---

Se déclenche après avoir notifié le joueur côté client.

```lua Event
AddEventHandler("vehicles_keys:notify", function(message, uncoloredMessage)

end)
```

### Paramètres

| Nom               | Type de donnée | Description                                                |
| ------------------ | --------- | ------------------------------------------------------------ |
| `message`          | string    | Message de la notification                                  |
| `uncoloredMessage` | string    | Message de la notification mais sans `~r~`, `~g~`, etc.   |

## Exemple

```lua
RegisterNetEvent("vehicles_keys:framework:ready", function()
    -- Désactive la notification par défaut du script (sinon il y aurait 2 notifications)
    exports["vehicles_keys"]:disableScriptEvent("vehicles_keys:notify")
end)

RegisterNetEvent("vehicles_keys:notify", function(message, uncoloredMessage)
    TriggerEvent("external_script:notify", message)
end)
```

<Note>
  Place ce code dans le fichier `integrations/cl_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
