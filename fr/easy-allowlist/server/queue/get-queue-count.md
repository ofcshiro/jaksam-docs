---
title: "Get queue count"
description: "Récupère le nombre de joueurs actuellement en queue."
icon: "hashtag"
---

Utilise l'export suivant si tu as besoin de récupérer **le nombre de joueurs actuellement en queue**.

```lua Export
-- Returns a number
exports["easy_allowlist"]:getQueueCount()
```

## Exemple

```lua
RegisterCommand("queuecount", function(source, args)
    local queueCount = exports["easy_allowlist"]:getQueueCount()
    print("Queue count: " .. queueCount)
end, false)
```

<Note>
  Tu peux ajouter ce code dans `sv_integrations.lua` du script ou dans n'importe quel autre fichier Lua côté serveur.
</Note>
