---
title: "Braquage démarré"
description: "Se déclenche quand un braquage commence."
icon: "play"
---

Se déclenche quand une étape est terminée dans la première phase d'un braquage qui n'a pas encore commencé.

```lua Event
RegisterNetEvent("robberies_creator:heist:heistStarted", function(heistId)

end)
```

### Paramètres

| Nom      | Type de donnée | Description        |
| --------- | --------- | --------------------- |
| `heistId` | integer   | ID du braquage        |

## Exemple

```lua
RegisterNetEvent("robberies_creator:heist:heistStarted", function(heistId)
    -- juste un exemple, ne fera rien d'utile, tu voudras peut-être récupérer des données depuis la base de données

    print("Heist with ID " .. heistId .. " has just started")
end)
```

<Note>
  Place ce code dans le fichier `integrations/sv_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
