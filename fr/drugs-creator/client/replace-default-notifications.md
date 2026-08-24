---
title: "Replace default notifications"
description: "Utilise un système de notifications personnalisé au lieu de celui par défaut en écoutant l'event notify."
icon: "bell"
---

Déclenché après avoir notifié le joueur côté client.

```lua Event
AddEventHandler("drugs_creator:notify", function(message, coloredMessage)

end)
```

### Paramètres

| Nom               | Type de donnée | Description                                                |
| ------------------- | --------- | ------------------------------------------------------------ |
| `message`           | string    | Message de la notification (sans couleur)                        |
| `coloredMessage`    | string    | Message de la notification mais avec `~r~`, `~g~`, etc.        |

## Exemple

```lua
RegisterNetEvent("drugs_creator:framework:ready", function()
    -- Désactive la notification par défaut du script (sinon il y aurait 2 notifications)
    exports["drugs_creator"]:disableScriptEvent("drugs_creator:notify")
end)

RegisterNetEvent("drugs_creator:notify", function(message, coloredMessage)
    TriggerEvent("external_script:notify", message)
end)
```

<Note>
  Place ce code dans le fichier `integrations/cl_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
