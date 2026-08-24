---
title: "Remplacer les notifications par défaut"
description: "Utilise un système de notifications personnalisé à la place du système par défaut en écoutant l'event notify."
icon: "bell"
---

Se déclenche après avoir notifié le joueur côté client.

```lua Event
AddEventHandler("races_creator:notify", function(message, uncoloredMessage)

end)
```

### Paramètres

| Nom               | Type de donnée | Description                                                |
| ------------------ | --------- | ------------------------------------------------------------ |
| `message`          | string    | Message de la notification                                  |
| `uncoloredMessage` | string    | Message de la notification mais sans `~r~`, `~g~`, etc.   |

## Exemple

```lua
RegisterNetEvent("races_creator:framework:ready", function()
    -- Désactive la notification par défaut du script (sinon il y aurait 2 notifications)
    exports["races_creator"]:disableScriptEvent("races_creator:notify")
end)

RegisterNetEvent("races_creator:notify", function(message, uncoloredMessage)
    TriggerEvent("external_script:notify", message)

    -- OU si tu NE veux PAS ~r~, ~g~ tu peux utiliser
    --TriggerEvent("external_script:notify", uncoloredMessage)
end)
```

<Note>
  Place ce code dans le fichier `integrations/cl_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
