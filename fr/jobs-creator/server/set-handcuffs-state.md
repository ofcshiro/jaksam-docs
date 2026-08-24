---
title: "Set handcuffs state"
description: "Définit directement l'état menotté d'un joueur, sans déclencher l'animation de menottage."
icon: "handcuffs"
---

Définit l'état des menottes d'un joueur, sans l'animation.

<CodeGroup>

```lua Export
exports["jobs_creator"]:setHandcuffs(playerId, state)
```

```lua Example
-- Ceci n'est qu'un exemple et ne fonctionnera pas, tu dois utiliser l'export correctement
RegisterNetEvent("hospital_script:playerDead", function(playerId)
    -- Le code du script
    -- Le code du script
    -- Le code du script

    -- Le joueur mort n'est plus menotté
    exports["jobs_creator"]:setHandcuffs(playerId, false)
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | integer | Le server ID du joueur cible |
| `state` | boolean | `true` = menotté, `false` = libre |
