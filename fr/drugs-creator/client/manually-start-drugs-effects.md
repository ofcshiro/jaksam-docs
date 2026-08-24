---
title: "Manually start drugs effects"
description: "Déclenche les effets des drogues manuellement, depuis le client ou le serveur."
icon: "wand-magic-sparkles"
---

Event pour démarrer les effets des drogues (tu préféreras peut-être le déclencher depuis le serveur).

```lua Event
TriggerEvent("drugs_creator:drugEffects", takingMethod, effects, effectsDuration, cumulativeEffects)
```

### Paramètres

| Nom                | Type de donnée | Description                                                                                        |
| -------------------- | --------- | -------------------------------------------------------------------------------------------------------- |
| `takingMethod`        | string    | Comment le joueur va prendre la drogue                                                                           |
| `effects`             | table     | Un tableau de chaînes contenant tous les effets que tu veux ajouter                                                  |
| `effectsDuration`     | integer   | Nombre de secondes pendant lesquelles les effets dureront                                                                                |
| `cumulativeEffects`   | table     | Optionnel. Tableau contenant les effets cumulatifs que tu veux ajouter (consulte les exemples pour le format)         |

### Méthodes de prise

- `"pill"`
- `"drink"`
- `"smoke"`
- `"needle"`

### Effets

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

### `actions` des effets cumulatifs

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

## Exemple — Côté client

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

    local effectsDuration = 120 -- secondes

    TriggerEvent("drugs_creator:drugEffects", takingMethod, effects, effectsDuration, cumulativeEffects)
end)
```

## Exemple — Côté serveur

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

    local effectsDuration = 120 -- secondes

    TriggerClientEvent("drugs_creator:drugEffects", playerId, takingMethod, effects, effectsDuration, cumulativeEffects)
end)
```
