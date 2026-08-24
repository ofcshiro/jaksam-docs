---
title: "Set handcuffs state"
description: "Establece directamente el estado de esposado de un jugador, sin disparar la animación de esposas."
icon: "handcuffs"
---

Establece el estado de esposas de un jugador, sin la animación.

<CodeGroup>

```lua Export
exports["jobs_creator"]:setHandcuffs(playerId, state)
```

```lua Example
-- Esto es solo un ejemplo y no funcionará, requiere que uses el export correctamente
RegisterNetEvent("hospital_script:playerDead", function(playerId)
    -- The script code
    -- The script code
    -- The script code

    -- El jugador muerto ya no está esposado
    exports["jobs_creator"]:setHandcuffs(playerId, false)
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerId` | integer | La ID de servidor del jugador objetivo |
| `state` | boolean | `true` = esposado, `false` = libre |
