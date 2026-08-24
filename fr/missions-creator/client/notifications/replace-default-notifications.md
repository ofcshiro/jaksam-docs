---
title: "Remplacer les notifications par défaut"
description: "Utilise un système de notifications personnalisé à la place du système par défaut en écoutant l'event notify."
icon: "bell"
---

Se déclenche après avoir notifié le joueur côté client.

```lua Event
AddEventHandler("missions_creator:notify", function(message, coloredMessage)

end)
```

### Paramètres

| Nom              | Type de donnée | Description                                                |
| ----------------- | --------- | ------------------------------------------------------------ |
| `message`         | string    | Message de la notification mais sans `~r~`, `~g~`, etc.   |
| `coloredMessage`  | string    | Message de la notification                                  |

## Exemple

```lua
RegisterNetEvent("missions_creator:framework:ready", function()
    -- Désactive la notification par défaut du script (sinon il y aurait 2 notifications)
    exports["missions_creator"]:disableScriptEvent("missions_creator:notify")
end)

RegisterNetEvent("missions_creator:notify", function(message, coloredMessage)
    TriggerEvent("external_script:notify", message)
end)
```

<Note>
  Place ce code dans le fichier `jaksam_core/config/cl_config.lua`, en bas du fichier sur de nouvelles lignes.
</Note>
