---
title: "Remplacer les notifications par défaut"
description: "Utilise un système de notifications personnalisé à la place du système par défaut en écoutant l'event notify."
icon: "bell"
---

Se déclenche après avoir notifié le joueur côté client.

```lua Event
AddEventHandler("dealerships_creator:notify", function(message, coloredMessage)

end)
```

### Paramètres

| Nom              | Type de donnée | Description                                              |
| ------------------ | --------- | ----------------------------------------------------------- |
| `message`          | string    | Message de la notification                                  |
| `coloredMessage`   | string    | Message de la notification mais avec `~r~`, `~g~`, etc.       |

## Exemple

```lua
RegisterNetEvent("dealerships_creator:framework:ready", function()
    -- Désactive la notification par défaut du script (sinon il y aurait 2 notifications)
    exports["dealerships_creator"]:disableScriptEvent("dealerships_creator:notify")
end)

RegisterNetEvent("dealerships_creator:notify", function(message, coloredMessage)
    TriggerEvent("external_script:notify", message)
end)
```

<Note>
  Place ce code dans le fichier `integrations/cl_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
