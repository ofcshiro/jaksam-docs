---
title: "Braquage terminé"
description: "Se déclenche quand un braquage est terminé."
icon: "flag-checkered"
---

Se déclenche quand un braquage est terminé (au même moment où la console du serveur affiche `"Heist has been completed"`).

```lua Event
RegisterNetEvent("robberies_creator:heist:heistFinished", function(heistId)

end)
```

### Paramètres

| Nom      | Type de donnée | Description        |
| --------- | --------- | --------------------- |
| `heistId` | integer   | ID du braquage        |

## Exemple

```lua
RegisterNetEvent("robberies_creator:heist:heistFinished", function(heistId)
    -- juste un exemple, ne fera rien d'utile, tu voudras peut-être récupérer des données depuis la base de données

    print("Heist with ID " .. heistId .. " is finished")
end)
```

<Note>
  Place ce code dans le fichier `integrations/sv_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
