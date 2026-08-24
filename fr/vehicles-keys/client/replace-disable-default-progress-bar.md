---
title: "Replace/Disable default progress bar"
description: "Remplace la barre de progression par défaut par la tienne, ou déclenche celle par défaut depuis des scripts externes."
icon: "spinner"
---

Se déclenche lors de l'utilisation de la barre de progression.

```lua Event
RegisterNetEvent("vehicles_keys:internalProgressBar", function(time, text)

end)
```

### Paramètres

| Nom   | Type de donnée | Description                       |
| ------ | --------- | ------------------------------------ |
| `time` | integer   | Durée de la barre de progression en secondes       |
| `text` | string    | Texte de description                        |

## Exemple

```lua
-- Dans vehicles_keys/integrations/cl_integrations.lua
RegisterNetEvent("vehicles_keys:framework:ready", function()
    -- Désactive la barre de progression par défaut du script (sinon il y aurait 2 barres de progression)
    exports["vehicles_keys"]:disableScriptEvent("vehicles_keys:internalProgressBar")
end)

-- Exemple pour remplacer la barre de progression du script par une externe
RegisterNetEvent("vehicles_keys:internalProgressBar", function(time, text)
    -- L'event pour activer ta barre de progression externe
    TriggerEvent("external_progressbar:start", time, text)
end)
```

<Note>
  Place ce code dans le fichier `integrations/cl_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
