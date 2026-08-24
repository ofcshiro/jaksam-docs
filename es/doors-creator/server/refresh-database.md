---
title: "Refresh database"
description: "Actualiza Doors Creator después de crear algo manualmente en la base de datos."
icon: "rotate"
---

Útil para actualizar Doors Creator después de crear algo manualmente en la base de datos.

```lua Export
exports["doors_creator"]:refreshDatabase()
```

## Ejemplo

```lua
RegisterCommand("refreshDoorsCreator", function(playerId)
    -- Solo la consola del servidor puede usar el comando
    if(playerId and playerId > 0) then return end

    exports["doors_creator"]:refreshDatabase()
end)
```
