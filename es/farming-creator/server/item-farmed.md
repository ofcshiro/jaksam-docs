---
title: "Item cosechado"
description: "Events que se activan después de que un jugador cosecha en cualquier lugar - farms, fields, foundries, seeds o workbenches."
icon: "wheat-awn"
---

Esta página enumera los events que se activan **después** de que un jugador cosecha en cualquier lugar.

### Farms

```lua
RegisterNetEvent("farming_creator:farms:completed", function(playerId, farmId, givenItems)
    -- Un ejemplo para un sistema de experiencia
    TriggerEvent("xp_system:addXp", playerId)
end)
```

### Fields

```lua
RegisterNetEvent("farming_creator:fields:completed", function(playerId, fieldId, givenItems)
    -- Un ejemplo para un sistema de experiencia
    TriggerEvent("xp_system:addXp", playerId)
end)
```

### Foundries

```lua
RegisterNetEvent("farming_creator:foundries:completed", function(playerId, foundryId, givenItems)
    -- Un ejemplo para un sistema de experiencia
    TriggerEvent("xp_system:addXp", playerId)
end)
```

### Seeds

```lua
RegisterNetEvent("farming_creator:seeds:interacted", function(playerId, seedId, givenItems)
    -- Un ejemplo para un sistema de experiencia
    TriggerEvent("xp_system:addXp", playerId)
end)
```

### Workbenches

```lua
RegisterNetEvent("farming_creator:workbenches:completed", function(playerId, workbenchId, givenItems)
    -- Un ejemplo para un sistema de experiencia
    TriggerEvent("xp_system:addXp", playerId)
end)
```
