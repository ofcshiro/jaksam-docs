---
title: "Police alerted"
description: "Se déclenche côté serveur, une fois par alerte, quand la police est alertée."
icon: "siren-on"
---

Se déclenche quand la police est alertée côté serveur (seulement **1** fois par alerte, au lieu de sur chaque joueur comme la version côté client).

```lua Event
RegisterNetEvent("vehicles_keys:alertedPolice", function(coords, message)

end)
```

### Paramètres

| Nom      | Type de donnée | Description                                |
| --------- | --------- | -------------------------------------------- |
| `coords`  | vector3   | Coordonnées où l'alerte a été déclenchée     |
| `message` | string    | Message qui serait affiché               |

## Exemple

```lua
RegisterNetEvent("vehicles_keys:alertedPolice", function(coords, message)
    -- juste un exemple, ne fonctionnera PAS
    TriggerClientEvent("news_script:heistAlert", -1, coords, message)
end)
```

<Note>
  Place ce code dans le fichier `integrations/sv_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
