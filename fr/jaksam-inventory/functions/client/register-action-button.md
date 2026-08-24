---
title: "Register action button"
description: "Enregistre un bouton d'action personnalisé dans la barre d'outils de l'interface de l'inventaire."
icon: "square-plus"
---

Enregistre un bouton d'action personnalisé dans la barre d'outils de l'interface de l'inventaire. Les boutons d'action apparaissent sur le côté droit de l'inventaire et peuvent déclencher n'importe quelle logique personnalisée au clic.

<Tip>
  Pour un guide complet avec images et exemples, consulte le [Guide des boutons d'action](/fr/jaksam-inventory/guides/action-buttons).
</Tip>

<CodeGroup>

```lua Export
exports['jaksam_inventory']:registerActionButton(id, icon, tooltip, onClick, visible)
```

```lua Example
-- Enregistre un bouton d'action simple
exports['jaksam_inventory']:registerActionButton(
    'my_custom_button',
    'bi-star-fill',
    'My Custom Action',
    function()
        print('Button clicked!')
        -- Ta logique personnalisée ici
    end
)

-- Enregistre un bouton caché (pour l'afficher plus tard selon des conditions)
exports['jaksam_inventory']:registerActionButton(
    'police_actions',
    'bi-shield-check',
    'Police Actions',
    function()
        TriggerEvent('myPoliceScript:openMenu')
    end,
    false -- caché par défaut
)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `id` | string | Identifiant unique du bouton. Utilisé pour référencer le bouton lors de son affichage/masquage/désenregistrement |
| `icon` | string | Nom de classe Bootstrap Icons (par ex. "bi-shield-x", "bi-car-front-fill"). Trouve des icônes sur [icons.getbootstrap.com](https://icons.getbootstrap.com/) |
| `tooltip` | string \| nil | Texte de l'infobulle affiché au survol du bouton. Peut être nil pour aucune infobulle |
| `onClick` | function | Fonction de callback exécutée quand le bouton est cliqué |
| `visible` | boolean \| nil | Si le bouton doit être visible initialement. Par défaut : true |

### Valeur de retour

Aucune.
