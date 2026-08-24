---
title: "Get queue count"
description: "Obtén el número de jugadores actualmente en la queue."
icon: "hashtag"
---

Usa el siguiente export si necesitas obtener **el número de jugadores actualmente en la queue**.

```lua Export
-- Devuelve un número
exports["easy_allowlist"]:getQueueCount()
```

## Ejemplo

```lua
RegisterCommand("queuecount", function(source, args)
    local queueCount = exports["easy_allowlist"]:getQueueCount()
    print("Queue count: " .. queueCount)
end, false)
```

<Note>
  Puedes añadir este código en `sv_integrations.lua` del script o en cualquier otro archivo Lua del lado del servidor.
</Note>
