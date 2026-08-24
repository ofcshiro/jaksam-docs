---
title: "Refresh database"
description: "Rafraîchit Doors Creator après avoir créé manuellement quelque chose dans la base de données."
icon: "rotate"
---

Utile pour rafraîchir Doors Creator après avoir créé manuellement quelque chose dans la base de données.

```lua Export
exports["doors_creator"]:refreshDatabase()
```

## Exemple

```lua
RegisterCommand("refreshDoorsCreator", function(playerId)
    -- Only server console can use the command
    if(playerId and playerId > 0) then return end

    exports["doors_creator"]:refreshDatabase()
end)
```
