---
title: "Barre de progression"
description: "Remplace la barre de progression par défaut avec la tienne, ou déclenche celle par défaut depuis des scripts externes."
icon: "spinner"
---

## Remplacer/Désactiver

Se déclenche lors de l'utilisation de la barre de progression.

```lua Event
RegisterNetEvent("farming_creator:internalProgressBar", function(time, text)

end)
```

### Paramètres

| Nom   | Type de donnée | Description                       |
| ------ | --------- | ---------------------------------- |
| `time` | integer   | Durée de la barre de progression en secondes   |
| `text` | string    | Texte de description                   |

### Exemple

```lua
-- Dans farming_creator/integrations/cl_integrations.lua
RegisterNetEvent("farming_creator:framework:ready", function()
    -- Désactive la barre de progression par défaut du script (sinon il y aurait 2 barres de progression)
    exports["farming_creator"]:disableScriptEvent("farming_creator:internalProgressBar")
end)

-- Exemple pour remplacer la barre de progression du script par une externe
RegisterNetEvent("farming_creator:internalProgressBar", function(time, text)
    -- L'event pour activer ta barre de progression externe
    TriggerEvent("external_progressbar:start", time, text)
end)
```

<Note>
  Place ce code dans le fichier `integrations/cl_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>

## Utilisation dans des scripts externes

Si tu aimes la barre de progression par défaut du script et veux l'utiliser dans des scripts externes, voici l'event :

```lua
TriggerEvent("farming_creator:startProgressBar", timeInMS, text, hexColor)
```

### Paramètres

| Nom       | Type de donnée | Description                                                                                            |
| ---------- | --------- | --------------------------------------------------------------------------------------------------------- |
| `timeInMS` | integer   | Durée de la barre de progression en millisecondes                                                              |
| `text`     | string    | Le texte qui sera affiché avec la barre de progression                                                         |
| `hexColor` | string    | La couleur de la barre de progression en code hex (exemple `#70f2b4`). Peut être `nil` pour utiliser la couleur par défaut du script |

### Exemple

```lua
-- Ceci va créer une commande pour afficher une barre de progression rouge
-- /progressbar 5000 Hello
RegisterCommand("progressbar", function(playerId, args)
    TriggerEvent("farming_creator:startProgressBar", tonumber(args[1]), args[2], "#ff0000")
end)
```
