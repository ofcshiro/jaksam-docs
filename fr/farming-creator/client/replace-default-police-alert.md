---
title: "Remplacer l'alerte police par défaut"
description: "Remplace le comportement d'alerte police côté client par le tien."
icon: "siren-on"
---

<Warning>
  Se déclenche quand la police est alertée. Ceci se déclenche sur le client de **chaque** policier — si tu cherches un event unique, regarde la catégorie côté serveur.
</Warning>

```lua Event
RegisterNetEvent("farming_creator:alertedPolice", function(coords, message)

end)
```

### Paramètres

| Nom      | Type de donnée | Description                                |
| --------- | --------- | -------------------------------------------- |
| `coords`  | vector3   | Coordonnées où l'alerte a été déclenchée     |
| `message` | string    | Le message que verrait le policier                |

## Exemple

```lua
-- Désactive l'alerte police par défaut
RegisterNetEvent("farming_creator:framework:ready", function()
    exports["farming_creator"]:disableScriptEvent("farming_creator:alertedPolice")
end)

RegisterNetEvent("farming_creator:alertedPolice", function(coords, message)
    -- Fais quelque chose
end)
```

<Note>
  Place ce code dans le fichier `integrations/cl_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
