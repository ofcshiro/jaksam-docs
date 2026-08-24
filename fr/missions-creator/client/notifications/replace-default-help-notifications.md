---
title: "Remplacer les notifications d'aide par défaut"
description: "Remplace la notification d'aide par défaut 'Press E to ...' par la tienne."
icon: "circle-info"
---

Sert à afficher le texte habituel `Press E to ...` en haut à gauche de l'écran du joueur.

```lua Export
exports["missions_creator"]:replaceShowHelpNotification(customFunction)
```

### Paramètres

| Nom             | Type de donnée | Description                                                                                                    |
| ---------------- | --------- | ------------------------------------------------------------------------------------------------------------- |
| `customFunction` | function  | Une fonction qui remplace la méthode par défaut `ESX.ShowHelpNotification`. **Nécessite** le paramètre message et est appelée à chaque frame |

## Exemple

```lua
local function myCustomHelpNotification(message)
    -- Personnalise ta fonction selon tes besoins
    print(message)

    ExternalScript.showHelpNotification(message)
end

RegisterNetEvent("missions_creator:framework:ready", function()
    -- Ceci remplacera la fonction de base par celle que tu veux
    exports["missions_creator"]:replaceShowHelpNotification(myCustomHelpNotification)
end)
```

<Note>
  Place ce code dans le fichier `jaksam_core/config/cl_config.lua`, en bas du fichier sur de nouvelles lignes.
</Note>
