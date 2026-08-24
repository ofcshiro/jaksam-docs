---
title: "Replace default mugshot notifications"
description: "Remplace la notification affichée quand un ped refuse une drogue pendant la vente aux PNJ."
icon: "id-card"
---

Notification affichée quand un ped refuse la drogue lors de la vente aux PNJ (notification avec le visage du ped).

```lua Event
AddEventHandler("drugs_creator:internalMugshotNotify", function(ped, title, message)

end)
```

### Paramètres

| Nom      | Type de donnée | Description                   |
| --------- | --------- | ---------------------------------- |
| `ped`     | integer   | Handle de l'entité du ped                     |
| `title`   | string    | Titre de la notification               |
| `message` | string    | Message de la notification              |

## Exemple

```lua
RegisterNetEvent("drugs_creator:framework:ready", function()
    -- Désactive la notification par défaut du script (sinon il y aurait 2 notifications)
    exports["drugs_creator"]:disableScriptEvent("drugs_creator:internalMugshotNotify")
end)

RegisterNetEvent("drugs_creator:internalMugshotNotify", function(ped, title, message)
    TriggerEvent("external_script:notify", message)
end)
```

<Note>
  Place ce code dans le fichier `integrations/cl_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
