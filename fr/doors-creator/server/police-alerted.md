---
title: "Police alerted"
description: "Déclenché côté serveur, une fois par alerte, quand la police est alertée."
icon: "siren-on"
---

Se déclenche quand la police est alertée côté serveur (seulement **1** fois par alerte, contrairement à la version côté client qui se déclenche pour chaque joueur).

```lua Event
RegisterNetEvent("doors_creator:alertedPolice", function(coords, message)

end)
```

### Paramètres

| Nom      | Type de donnée | Description                                |
| --------- | --------- | -------------------------------------------- |
| `coords`  | vector3   | Coordonnées où l'alerte a été déclenchée     |
| `message` | string    | Message qui serait affiché               |

## Exemple

```lua
RegisterNetEvent("doors_creator:alertedPolice", function(coords, message)
    -- just an example, will NOT work
    TriggerClientEvent("news_script:heistAlert", -1, coords, message)
end)
```

<Note>
  Place ce code dans le fichier `integrations/sv_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
