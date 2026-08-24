---
title: "Get queue info"
description: "Récupère les données des joueurs actuellement en queue."
icon: "circle-info"
---

Utilise l'export suivant pour récupérer les données des joueurs actuellement en queue (pseudo, identifier, priorité, etc.).

```lua Export
-- Returns a table
exports["easy_allowlist"]:getPlayersInQueue()
```

## Exemple

```lua
RegisterCommand("queueinfo", function(source, args)
    local queueInfo = exports["easy_allowlist"]:getPlayersInQueue()
    print(json.encode(queueInfo, { indent = true }))
end, false)
```

<Note>
  Tu peux ajouter ce code dans `sv_integrations.lua` du script ou dans n'importe quel autre fichier Lua côté serveur.
</Note>
