---
title: "Remplacer les notifications mugshot par défaut"
description: "Remplace la notification affichée pour l'action 'parler au ped' (avec le visage du PNJ)."
icon: "id-card"
---

Notification affichée lors de l'utilisation de l'action "parler au ped" (notification avec le visage du PNJ).

```lua Event
AddEventHandler("missions_creator:internalMugshotNotify", function(ped, title, message)

end)
```

### Paramètres

| Nom      | Type de donnée | Description                   |
| --------- | --------- | -------------------------------- |
| `ped`     | integer   | Handle de l'entité ped                |
| `title`   | string    | Titre de la notification         |
| `message` | string    | Message de la notification       |

## Exemple

```lua
RegisterNetEvent("missions_creator:framework:ready", function()
    -- Désactive la notification par défaut du script (sinon il y aurait 2 notifications)
    exports["missions_creator"]:disableScriptEvent("missions_creator:internalMugshotNotify")
end)

RegisterNetEvent("missions_creator:internalMugshotNotify", function(ped, title, message)
    TriggerEvent("external_script:notify", message)
end)
```

<Note>
  Place ce code dans le fichier `jaksam_core/config/cl_config.lua`, en bas du fichier sur de nouvelles lignes.
</Note>
