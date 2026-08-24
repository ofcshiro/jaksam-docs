---
title: "Barre de progression"
description: "Remplace la barre de progression par défaut par la tienne, ou déclenche celle par défaut depuis des scripts externes."
icon: "spinner"
---

## Comment la remplacer ?

Tu peux utiliser un [module](/fr/robberies-creator/modules) de Robberies Creator si tu veux utiliser ta propre barre de progression.

## Utilisation dans des scripts externes

Si tu aimes la barre de progression par défaut du script et veux l'utiliser dans des scripts externes, voici l'event :

```lua
TriggerEvent("robberies_creator:startProgressBar", timeInMS, text, hexColor)
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
    TriggerEvent("robberies_creator:startProgressBar", tonumber(args[1]), args[2], "#ff0000")
end)
```
