---
title: "Item récolté"
description: "Events déclenchés après qu'un joueur récolte n'importe où - fermes, champs, fonderies, graines ou établis."
icon: "wheat-awn"
---

Cette page liste les events déclenchés **après** qu'un joueur récolte n'importe où.

### Fermes

```lua
RegisterNetEvent("farming_creator:farms:completed", function(playerId, farmId, givenItems)
    -- Un exemple pour un système d'xp
    TriggerEvent("xp_system:addXp", playerId)
end)
```

### Champs

```lua
RegisterNetEvent("farming_creator:fields:completed", function(playerId, fieldId, givenItems)
    -- Un exemple pour un système d'xp
    TriggerEvent("xp_system:addXp", playerId)
end)
```

### Fonderies

```lua
RegisterNetEvent("farming_creator:foundries:completed", function(playerId, foundryId, givenItems)
    -- Un exemple pour un système d'xp
    TriggerEvent("xp_system:addXp", playerId)
end)
```

### Graines

```lua
RegisterNetEvent("farming_creator:seeds:interacted", function(playerId, seedId, givenItems)
    -- Un exemple pour un système d'xp
    TriggerEvent("xp_system:addXp", playerId)
end)
```

### Établis

```lua
RegisterNetEvent("farming_creator:workbenches:completed", function(playerId, workbenchId, givenItems)
    -- Un exemple pour un système d'xp
    TriggerEvent("xp_system:addXp", playerId)
end)
```
