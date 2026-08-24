---
title: "Étape terminée"
description: "Se déclenche quand une étape d'un braquage est terminée."
icon: "circle-check"
---

Se déclenche quand une étape d'un braquage est terminée.

```lua Event
RegisterNetEvent("robberies_creator:heist:stepCompleted", function(playerId, heistId, stageId, stepType)

end)
```

### Paramètres

| Nom       | Type de donnée | Description                                                                              |
| ---------- | --------- | -------------------------------------------------------------------------------------------- |
| `playerId` | integer   | Server ID du joueur qui a terminé l'étape                                                       |
| `heistId`  | integer   | ID du braquage                                                                                        |
| `stageId`  | integer   | ID de la phase                                                                                        |
| `stepType` | string    | Le type d'étape. Les types d'étapes disponibles sont listés [ci-dessous](#types-detape)                            |

### Types d'étape

- `SAFE`
- `ROBBABLE_OBJECT`
- `HACKABLE_PANEL`
- `THERMAL_CHARGE`
- `LOCKPICKABLE_DOOR`

## Exemple

```lua
-- Cet exemple hypothétique donne de l'xp quand un joueur termine une étape avec un minijeu
RegisterNetEvent("robberies_creator:heist:stepCompleted", function(playerId, heistId, stageId, stepType)
    if(stepType ~= "ROBBABLE_OBJECT") then
        TriggerEvent("xp_script:addPlayerXp", playerId, 10)
    end
end)
```

<Note>
  Place ce code dans le fichier `integrations/sv_integrations.lua` du script, en bas du fichier sur de nouvelles lignes.
</Note>
