---
title: "Boutons d'action"
icon: "square-plus"
description: "Ajoute des boutons personnalisés toujours visibles dans la barre d'outils de l'inventaire pour des menus, jobs et actions rapides"
---

Les boutons d'action sont des boutons personnalisés qui apparaissent dans la barre d'outils de l'interface d'inventaire. Contrairement aux [Actions contextuelles](/fr/jaksam-inventory/guides/context-actions) (qui apparaissent lors d'un clic droit sur un item), les boutons d'action sont toujours visibles dans l'en-tête de l'inventaire et peuvent déclencher n'importe quelle logique personnalisée.

<Columns cols={2}>
  <Frame>
    ![Action buttons screenshot](/images/action-buttons-1.jpg)
  </Frame>

  <Frame>
    ![Action buttons 2nd screenshot](/images/action-buttons-2.jpg)
  </Frame>
</Columns>

## Quand utiliser les boutons d'action

Utilise les boutons d'action quand tu as besoin :

- D'un bouton toujours visible dans l'inventaire (pas spécifique à un item)
- D'un accès rapide à des fonctionnalités comme "Menu police", "Garage", "Craft", etc.
- D'actions spécifiques à un job ou un rôle

## Utilisation de base

### Enregistrer un bouton

```lua
exports['jaksam_inventory']:registerActionButton(
    'my_button',           -- ID unique
    'bi-star-fill',        -- Classe Bootstrap Icons
    'My Tooltip',          -- Info-bulle au survol (ou nil)
    function()             -- Callback au clic
        print('Clicked!')
    end,
    true                   -- Visible (par défaut : true)
)
```

### Retirer un bouton

```lua
exports['jaksam_inventory']:unregisterActionButton('my_button')
```

### Afficher/masquer sans retirer

```lua
-- Masquer (le bouton reste enregistré, juste invisible)
exports['jaksam_inventory']:hideActionButton('my_button')

-- Réafficher
exports['jaksam_inventory']:showActionButton('my_button')
```

## Exemples pratiques

<Tabs>
  <Tab title="Spécifique à un job (Police)">
    Enregistre le bouton une fois au démarrage de la resource, puis affiche/masque selon le job :

    ```lua
        -- Enregistrement au démarrage de la resource (masqué par défaut)
        CreateThread(function()
            exports['jaksam_inventory']:registerActionButton(
                'police_menu',
                'bi-shield-check',
                'Police Actions',
                function()
                    TriggerEvent('police:openActionsMenu')
                end,
                false -- Démarre masqué
            )
        end)
    
        -- Affiche/masque selon les changements de job
        AddEventHandler('esx:setJob', function(job)
            if job.name == 'police' then
                exports['jaksam_inventory']:showActionButton('police_menu')
            else
                exports['jaksam_inventory']:hideActionButton('police_menu')
            end
        end)
    
        -- Vérifie aussi au chargement du joueur
        RegisterNetEvent('esx:playerLoaded', function(xPlayer)
            if xPlayer.job.name == 'police' then
                exports['jaksam_inventory']:showActionButton('police_menu')
            end
        end)
    ```
  </Tab>
  <Tab title="Ouvrir une planque">
    ```lua
        exports['jaksam_inventory']:registerActionButton(
            'open_personal_stash',
            'bi-box-seam',
            'Personal Stash',
            function()
                exports['jaksam_inventory']:openInventory('personal_stash_' .. GetPlayerServerId(PlayerId()))
            end
        )
    ```
  </Tab>
  <Tab title="Menu de craft">
    ```lua
        exports['jaksam_inventory']:registerActionButton(
            'crafting_menu',
            'bi-hammer',
            'Crafting',
            function()
                TriggerEvent('crafting:openMenu')
            end
        )
    ```
  </Tab>
  <Tab title="Plusieurs boutons de job">
    ```lua
        local jobButtons = {
            police = { id = 'btn_police', icon = 'bi-shield-check', tooltip = 'Police Menu', event = 'police:menu' },
            ambulance = { id = 'btn_ambulance', icon = 'bi-heart-pulse', tooltip = 'EMS Menu', event = 'ambulance:menu' },
            mechanic = { id = 'btn_mechanic', icon = 'bi-tools', tooltip = 'Mechanic Tools', event = 'mechanic:menu' },
        }
    
        -- Enregistre tous les boutons masqués
        CreateThread(function()
            for _, btn in pairs(jobButtons) do
                exports['jaksam_inventory']:registerActionButton(
                    btn.id,
                    btn.icon,
                    btn.tooltip,
                    function()
                        TriggerEvent(btn.event)
                    end,
                    false
                )
            end
        end)
    
        -- Affiche le bon bouton selon le job
        AddEventHandler('esx:setJob', function(job)
            -- Masque tous les boutons de job
            for _, btn in pairs(jobButtons) do
                exports['jaksam_inventory']:hideActionButton(btn.id)
            end
    
            -- Affiche celui du job actuel (s'il existe)
            if jobButtons[job.name] then
                exports['jaksam_inventory']:showActionButton(jobButtons[job.name].id)
            end
        end)
    ```
  </Tab>
</Tabs>

## Notes importantes

<CardGroup cols={1}>
  <Card title="IDs uniques" icon="fingerprint">
    Chaque bouton doit avoir un ID unique. Enregistrer avec le même ID écrasera le bouton précédent.
  </Card>

  <Card title="Persistance" icon="rotate">
    Les boutons survivent à l'ouverture/fermeture de l'inventaire mais sont perdus au redémarrage de la resource. Réenregistre-les au démarrage de ta resource.
  </Card>

  <Card title="Performance" icon="gauge-high">
    N'enregistre/désenregistre pas les boutons de manière répétée. Enregistre-les une fois, puis utilise show/hide pour basculer leur visibilité.
  </Card>
</CardGroup>
