---
title: "Manually start drugs effects"
description: "Activa los efectos de las drogas manualmente, desde el lado del cliente o del servidor."
icon: "wand-magic-sparkles"
---

Event para iniciar los efectos de las drogas (puede que prefieras activarlo desde el lado del servidor).

```lua Event
TriggerEvent("drugs_creator:drugEffects", takingMethod, effects, effectsDuration, cumulativeEffects)
```

### Parámetros

| Nombre                | Tipo de dato | Descripción                                                                                        |
| -------------------- | --------- | -------------------------------------------------------------------------------------------------------- |
| `takingMethod`        | string    | Cómo consumirá la droga el jugador                                                                           |
| `effects`             | table     | Un array de strings con todos los efectos que quieres añadir                                                  |
| `effectsDuration`     | integer   | Segundos que durarán los efectos                                                                                |
| `cumulativeEffects`   | table     | Opcional. Array con los efectos acumulativos que quieres añadir (revisa los ejemplos para ver el formato)         |

### Métodos de consumo

- `"pill"`
- `"drink"`
- `"smoke"`
- `"needle"`

### Efectos

- `"visual_shaking"`
- `"drunk_walk"`
- `"fall"`
- `"pink_visual"`
- `"green_visual"`
- `"confused_visual"`
- `"yellow_visual"`
- `"blurred_visual"`
- `"red_visual"`
- `"foggy_visual"`
- `"blue_visual"`
- `"armor50"`
- `"armor100"`
- `"health50"`
- `"health100"`
- `"sprint_faster"`
- `"swim_faster"`
- `"infinite_stamina"`
- `"remove_old_effects"`
- `"vehicle_stalker"`
- `"ghost"`

### `actions` de efectos acumulativos

- `increaseArmor`
- `decreaseArmor`
- `increaseHealth`
- `decreaseHealth`
- `increaseHunger`
- `decreaseHunger`
- `increaseThirst`
- `decreaseThirst`
- `increaseStress`
- `decreaseStress`

## Ejemplo — Lado del cliente

```lua
RegisterCommand("effects", function()
    local takingMethod = "pill"
    local effects = {
        "drunk_walk",
        "swim_faster",
        "green_visual",
    }

    local cumulativeEffects = {
        {action = "increaseArmor", value = 50},
        {action = "decreaseThirst", value = 15},
    }

    local effectsDuration = 120 -- segundos

    TriggerEvent("drugs_creator:drugEffects", takingMethod, effects, effectsDuration, cumulativeEffects)
end)
```

## Ejemplo — Lado del servidor

```lua
RegisterCommand("effects", function(playerId)
    local takingMethod = "pill"
    local effects = {
        "drunk_walk",
        "swim_faster",
        "green_visual",
    }

    local cumulativeEffects = {
        {action = "increaseArmor", value = 50},
        {action = "decreaseThirst", value = 15},
    }

    local effectsDuration = 120 -- segundos

    TriggerClientEvent("drugs_creator:drugEffects", playerId, takingMethod, effects, effectsDuration, cumulativeEffects)
end)
```
