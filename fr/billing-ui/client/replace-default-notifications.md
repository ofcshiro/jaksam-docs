---
title: "Remplacer les notifications par défaut"
description: "Utilise un système de notifications personnalisé à la place du système par défaut en écoutant l'event notify."
icon: "bell"
---

Se déclenche après avoir notifié le joueur côté client.

```lua Event
AddEventHandler("billing_ui:notify", function(message, uncoloredMessage)

end)
```

### Paramètres

| Nom               | Type de donnée | Description                                                |
| ------------------ | --------- | ------------------------------------------------------------ |
| `message`          | string    | Message de la notification                                  |
| `uncoloredMessage` | string    | Message de la notification mais sans `~r~`, `~g~`, etc.   |

## Exemple

```lua
RegisterNetEvent("billing_ui:framework:ready", function()
    -- Désactive la notification par défaut du script (sinon il y aurait 2 notifications)
    exports["billing_ui"]:disableScriptEvent("billing_ui:notify")
end)

RegisterNetEvent("billing_ui:notify", function(message, uncoloredMessage)
    TriggerEvent("external_script:notify", message)
end)
```

<Note>
  Place ce code dans le fichier `integrations/cl_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
