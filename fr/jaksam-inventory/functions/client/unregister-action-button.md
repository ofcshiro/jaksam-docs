---
title: "Unregister action button"
description: "Supprime un bouton d'action précédemment enregistré de l'interface de l'inventaire."
icon: "square-minus"
---

Supprime un bouton d'action précédemment enregistré de l'interface de l'inventaire.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:unregisterActionButton(id)
```

```lua Example
-- Désenregistre un bouton lorsqu'il n'est plus nécessaire
exports['jaksam_inventory']:unregisterActionButton('my_custom_button')

-- Désenregistre quand le joueur quitte un job
AddEventHandler('esx:setJob', function(job)
    if job.name ~= 'police' then
        exports['jaksam_inventory']:unregisterActionButton('police_actions')
    end
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `id` | string | L'identifiant unique du bouton à supprimer (même id utilisé dans `registerActionButton`) |

### Valeur de retour

Aucune.
