---
title: "Remplacer l'alerte police par défaut"
description: "Remplace le comportement d'alerte police côté client par le tien."
icon: "siren-on"
---

<Warning>
  Se déclenche quand la police est alertée. Ceci se déclenche sur le client de **chaque** policier — si tu cherches un event unique, regarde la catégorie côté serveur.
</Warning>

```lua Event
RegisterNetEvent("missions_creator:alertedPolice", function(coords, message)

end)
```

### Paramètres

| Nom      | Type de donnée | Description                     |
| --------- | --------- | ---------------------------------- |
| `coords`  | vector3   | Coordonnées à envoyer à la police       |
| `message` | string    | Le message que verra le policier        |

## Exemple

```lua
-- Désactive l'alerte police par défaut
RegisterNetEvent("missions_creator:framework:ready", function()
    exports["missions_creator"]:disableScriptEvent("missions_creator:alertedPolice")
end)

RegisterNetEvent("missions_creator:alertedPolice", function(coords, message)
    -- Fais quelque chose
end)
```

<Note>
  Place ce code dans le fichier `jaksam_core/config/cl_config.lua`, en bas du fichier sur de nouvelles lignes.
</Note>
