---
title: "Get queue info"
description: "Obtén los datos de los jugadores que están actualmente en la queue."
icon: "circle-info"
---

Usa el siguiente export para obtener los datos de los jugadores que están actualmente en la queue (nickname, identifier, prioridad, etc.).

```lua Export
-- Devuelve una tabla
exports["easy_allowlist"]:getPlayersInQueue()
```

## Ejemplo

```lua
RegisterCommand("queueinfo", function(source, args)
    local queueInfo = exports["easy_allowlist"]:getPlayersInQueue()
    print(json.encode(queueInfo, { indent = true }))
end, false)
```

<Note>
  Puedes añadir este código en `sv_integrations.lua` del script o en cualquier otro archivo Lua del lado del servidor.
</Note>
