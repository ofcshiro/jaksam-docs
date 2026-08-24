---
title: "Show action button"
description: "Rend visible un bouton d'action précédemment caché dans l'interface de l'inventaire."
icon: "eye"
---

Rend visible un bouton d'action précédemment caché dans l'interface de l'inventaire.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:showActionButton(id)
```

```lua Example
-- Affiche un bouton qui avait été enregistré comme caché
exports['jaksam_inventory']:showActionButton('police_actions')

-- Affiche le bouton quand le joueur obtient un job spécifique
AddEventHandler('esx:setJob', function(job)
    if job.name == 'police' then
        exports['jaksam_inventory']:showActionButton('police_actions')
    end
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `id` | string | L'identifiant unique du bouton à afficher |

### Valeur de retour

Aucune.
