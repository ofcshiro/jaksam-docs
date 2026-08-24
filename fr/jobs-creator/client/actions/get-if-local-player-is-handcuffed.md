---
title: "Get if local player is handcuffed"
description: "Vérifie si le joueur local est actuellement menotté."
icon: "handcuffs"
---

Retourne si le client/joueur **local** est menotté.

<CodeGroup>

```lua Export
exports["jobs_creator"]:isPlayerHandcuffed()
```

```lua Example
-- This code will continuously check if the local (self) player is handcuffed
-- If so, specified controls will be disabled
Citizen.CreateThread(function()
    while true do
        Citizen.Wait(0)

        if(exports["jobs_creator"]:isPlayerHandcuffed())then
            DisableControlAction(0, 22, true) -- Disable jump
        end
    end
end)
```

</CodeGroup>

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `isHandcuffed` | boolean | `true` si le joueur est menotté, `false` si le joueur n'est **pas** menotté |

### Où insérer le code ?

Tu peux placer le code dans n'importe quel fichier client de tes scripts.
