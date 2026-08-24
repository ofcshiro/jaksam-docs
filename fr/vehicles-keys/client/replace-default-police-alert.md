---
title: "Replace default police alert"
description: "Remplace le comportement de l'alerte police côté client par le tien."
icon: "siren-on"
---

<Warning>
  Se déclenche quand la police est alertée. Ceci se déclenche sur le client de **chaque** policier — si tu cherches un event unique, consulte la catégorie côté serveur.
</Warning>

```lua Event
RegisterNetEvent("vehicles_keys:alertedPolice", function(coords, message)

end)
```

### Paramètres

| Nom      | Type de donnée | Description                                |
| --------- | --------- | -------------------------------------------- |
| `coords`  | vector3   | Coordonnées où l'alerte a été déclenchée     |
| `message` | string    | Le message que le policier verra                  |

## Exemple

```lua
-- Désactive l'alerte police par défaut
RegisterNetEvent("vehicles_keys:framework:ready", function()
    exports["vehicles_keys"]:disableScriptEvent("vehicles_keys:alertedPolice")
end)

RegisterNetEvent("vehicles_keys:alertedPolice", function(coords, message)
    -- Fais quelque chose
end)
```

<Note>
  Place ce code dans le fichier `integrations/cl_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
