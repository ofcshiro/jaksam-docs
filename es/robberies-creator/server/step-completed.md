---
title: "Paso completado"
description: "Se activa cuando se completa un paso de un robo."
icon: "circle-check"
---

Se activa cuando se completa un paso de un robo.

```lua Event
RegisterNetEvent("robberies_creator:heist:stepCompleted", function(playerId, heistId, stageId, stepType)

end)
```

### Parámetros

| Nombre       | Tipo de dato | Descripción                                                                              |
| ---------- | --------- | -------------------------------------------------------------------------------------------- |
| `playerId` | integer   | Server ID del jugador que completó el paso                                                       |
| `heistId`  | integer   | ID del robo                                                                                        |
| `stageId`  | integer   | ID de la etapa                                                                                        |
| `stepType` | string    | El tipo de paso. Los tipos de paso disponibles se listan [abajo](#tipos-de-paso)                            |

### Tipos de paso

- `SAFE`
- `ROBBABLE_OBJECT`
- `HACKABLE_PANEL`
- `THERMAL_CHARGE`
- `LOCKPICKABLE_DOOR`

## Ejemplo

```lua
-- Este ejemplo hipotético da xp cuando un jugador completa un paso que tiene un minijuego
RegisterNetEvent("robberies_creator:heist:stepCompleted", function(playerId, heistId, stageId, stepType)
    if(stepType ~= "ROBBABLE_OBJECT") then
        TriggerEvent("xp_script:addPlayerXp", playerId, 10)
    end
end)
```

<Note>
  Coloca este código en el archivo `integrations/sv_integrations.lua` del script, al final del archivo en líneas nuevas.
</Note>
