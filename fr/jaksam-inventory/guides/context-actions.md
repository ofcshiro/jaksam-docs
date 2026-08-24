---
title: "Actions contextuelles"
icon: "hand-pointer"
description: "Ajoute des boutons de clic droit personnalisés aux items, individuellement ou par type d'item"
---

Les actions contextuelles sont des boutons personnalisés qui apparaissent quand tu fais un clic droit sur un item dans ton inventaire. Elles permettent aux joueurs d'effectuer des actions spécifiques sur les items, comme utiliser, inspecter, ou tout comportement personnalisé que tu souhaites.

<Columns cols={2}>
  <Frame>
    ![Item context actions screenshot](/images/context-actions-screenshot.png)
  </Frame>

  <Frame>
    ![Item context actions code screenshot](/images/context-actions-code.png)
  </Frame>
</Columns>

## Quand utiliser chaque méthode

<CardGroup cols={2}>
  <Card title="Item unique" icon="circle-dot">
    À utiliser quand tu veux des boutons pour UN seul item spécifique (par exemple, uniquement sur l'item "water")
  </Card>

  <Card title="Par type" icon="layer-group">
    À utiliser quand tu veux les mêmes boutons sur TOUS les items du même type (par exemple, toutes les armes, tous les containers)
  </Card>
</CardGroup>

## Méthode 1 : ajouter des boutons à un seul item

Pour ajouter des boutons personnalisés à un item spécifique, ouvre `jaksam_inventory/_data/items.lua` et trouve ou crée ton item. Ajoute la propriété `contextActions` :

```lua
['water'] = {
    label = 'Water',
    weight = 1.0,
    stackable = true,
    close = true,
    description = 'A bottle of water',
    maxStack = 10,
    contextActions = {
        {
            label = 'Drink',                    -- Texte du bouton que voient les joueurs
            icon = 'bi-droplet',                -- Icône (Bootstrap Icons)
            callback = function(inventoryId, slotIndex)
                -- Ton code ici - s'exécute quand le bouton est cliqué
                TriggerServerEvent('myserver:drinkWater', inventoryId, slotIndex)
            end
        },
        {
            label = 'Check expiration',
            icon = 'bi-calendar-check',
            callback = function(inventoryId, slotIndex)
                print('Checking expiration date...')
                -- Ajoute ta logique ici
            end
        }
    }
},
```

<Note>
  **Notes importantes :**

  - `inventoryId` : identifie dans quel inventaire se trouve l'item (inventaire du joueur, coffre de véhicule, etc.)
  - `slotIndex` : le numéro du slot où se trouve l'item
  - `icon` : utilise Bootstrap Icons (cherche "bootstrap icons" en ligne pour trouver des noms d'icônes)
</Note>

## Méthode 2 : ajouter des boutons à tous les items d'un type spécifique

Si tu veux que les mêmes boutons apparaissent sur TOUS les items du même type (comme toutes les armes, tous les items de nourriture, etc.), utilise le système de defaults.

Ouvre `jaksam_inventory/_data/defaults.lua` et ajoute ou modifie le type que tu veux :

```lua
Script.defaultsByType = {
    ['weapon'] = {
        displayFields = {
            -- ... champs d'affichage existants ...
        },
        contextActions = {
            {
                label = 'Empty ammo',
                icon = 'bi-asterisk',
                callback = function(inventoryId, slotIndex)
                    TriggerServerEvent(Utils.eventsPrefix .. ":emptyAmmo", inventoryId, slotIndex)
                end
            },
            {
                label = 'View components',
                icon = 'bi-eye',
                callback = function(inventoryId, slotIndex)
                    Script.closeInventoryUI()
                    Script.viewComponents(inventoryId, slotIndex)
                end
            }
        }
    },

    ['food'] = {
        contextActions = {
            {
                label = 'Eat',
                icon = 'bi-egg-fried',
                callback = function(inventoryId, slotIndex)
                    TriggerServerEvent('myserver:eatFood', inventoryId, slotIndex)
                end
            }
        }
    },
}
```

Cela signifie :

- TOUS les items avec `type = 'weapon'` auront les boutons "Empty ammo" et "View components"
- TOUS les items avec `type = 'food'` auront un bouton "Eat"

## Ajouter des boutons globaux à TOUS les items

Tu peux aussi ajouter des boutons qui apparaissent sur CHAQUE item du jeu en utilisant la clé spéciale `['*']` :

```lua
Script.defaultsByType = {
    ['*'] = {
        contextActions = {
            {
                label = 'Inspect',
                icon = 'bi-search',
                callback = function(inventoryId, slotIndex)
                    print('Inspecting item...')
                    -- Ton code ici
                end
            }
        }
    },
}
```
