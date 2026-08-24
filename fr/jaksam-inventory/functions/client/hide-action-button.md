---
title: "Hide action button"
description: "Cache un bouton d'action de l'interface de l'inventaire sans le supprimer."
icon: "eye-slash"
---

Cache un bouton d'action de l'interface de l'inventaire sans le supprimer.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:hideActionButton(id)
```

```lua Example
-- Cache un bouton temporairement
exports['jaksam_inventory']:hideActionButton('police_actions')

-- Cache le bouton quand le joueur n'est plus en service
AddEventHandler('esx:setJob', function(job)
    if job.name ~= 'police' then
        exports['jaksam_inventory']:hideActionButton('police_actions')
    end
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `id` | string | L'identifiant unique du bouton à cacher |

### Valeur de retour

Aucune.
