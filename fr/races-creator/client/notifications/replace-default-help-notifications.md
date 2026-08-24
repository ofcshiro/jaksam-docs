---
title: "Remplacer les notifications d'aide par défaut"
description: "Remplace la notification d'aide par défaut 'Press E to ...' par la tienne."
icon: "circle-info"
---

Sert à afficher le texte habituel `Press E to ...` en haut à gauche de l'écran du joueur.

```lua Export
exports["races_creator"]:replaceShowHelpNotification(customFunction)
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

RegisterNetEvent("races_creator:framework:ready", function()
    -- Ceci remplacera la fonction de base par celle que tu veux
    exports["races_creator"]:replaceShowHelpNotification(myCustomHelpNotification)
end)
```

<Note>
  Place ce code dans le fichier `integrations/cl_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
