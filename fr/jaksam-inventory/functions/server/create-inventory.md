---
title: "Create inventory"
description: "Crée un nouvel inventaire en base de données et/ou en mémoire (selon les options)."
icon: "square-plus"
---

Crée un nouvel inventaire en base de données et/ou en mémoire (selon les options). Si un inventaire avec le même ID existe déjà, celui-ci est renvoyé tel quel sans être modifié.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:createInventory(id, label, options, items, inventoryType, metadata)
```

```lua Example
-- Exemple : Crée une caisse de butin avec du loot dynamique selon la rareté
-- N'oublie pas de sécuriser l'event d'une manière ou d'une autre selon ton cas d'usage, sinon les tricheurs pourront simplement déclencher l'event pour obtenir du loot gratuit
RegisterNetEvent('myresource:openLootCrate', function(rarity)
    local playerId = source

    -- Définit les pools de loot selon la rareté
    local lootPools = {
        common = {
            minTypes = 1,
            maxTypes = 2,
            items = {
                { name = "water",   chance = 15, min = 1, max = 3 },
                { name = "bread",   chance = 15, min = 1, max = 2 },
                { name = "bandage", chance = 10, min = 1, max = 2 },
            }
        },
        rare = {
            minTypes = 2,
            maxTypes = 4,
            items = {
                { name = "water",         chance = 10, min = 2, max = 4 },
                { name = "bread",         chance = 8,  min = 2, max = 3 },
                { name = "bandage",       chance = 8,  min = 2, max = 3 },
                { name = "lockpick",      chance = 5,  min = 1, max = 2 },
                { name = "weapon_pistol", chance = 2,  min = 1, max = 1 },
            }
        },
        legendary = {
            minTypes = 3,
            maxTypes = 5,
            items = {
                { name = "water",         chance = 8,  min = 3, max = 5 },
                { name = "bandage",       chance = 8,  min = 3, max = 4 },
                { name = "lockpick",      chance = 6,  min = 2, max = 3 },
                { name = "weapon_pistol", chance = 4,  min = 1, max = 1 },
                { name = "weapon_rifle",  chance = 2,  min = 1, max = 1 },
            }
        }
    }

    local selectedLoot = lootPools[rarity] or lootPools.common

    local inventory = exports['jaksam_inventory']:createInventory(
        nil, -- Génère l'ID automatiquement
        "Loot Crate (" .. rarity .. ")", -- Libellé dynamique
        {
            temporary = true, -- L'inventaire sera perdu au redémarrage du script
            maxSlots = 5,
            maxWeight = 50.0,
            disableIncoming = true, -- Le joueur ne peut pas ajouter d'objets à cet inventaire
            prefillItems = selectedLoot,
            revealItems = {
                delayPerItem = 1000,
                randomOrder = true
            }
        },
        nil,
        'stash',
        nil
    )

    -- Ouvre l'interface de l'inventaire pour le joueur
    if inventory then
        exports['jaksam_inventory']:forceOpenInventory(playerId, inventory.id)
    end
end)
```

```lua Example: persistent stash
-- Crée une stash persistante avec des objets de départ fixes
local inventory = exports['jaksam_inventory']:createInventory(
    "welcome_kit_" .. charId,
    "Welcome Kit",
    { maxSlots = 5, maxWeight = 20.0 },
    {
        {"bread", 3, nil},
        {"water", 2, nil},
    },
    'stash',
    nil
)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `id` | string \| nil | Identifiant unique de l'inventaire. Si nil, un ID aléatoire est généré |
| `label` | string \| nil | Nom affiché de l'inventaire. Si nil, une traduction basée sur le type d'inventaire sera utilisée |
| `options` | table | Options de configuration de l'inventaire (voir les Notes ci-dessous) |
| `items` | table | Objets statiques à ajouter lors de la première création de l'inventaire. Format tableau : `{{itemName, amount, metadata}, ...}`. Ignoré si l'inventaire existe déjà en base de données |
| `inventoryType` | string | Type d'inventaire. Par défaut : "stash". Autres valeurs : "player", "trunk", "glovebox" |
| `metadata` | table | Métadonnées supplémentaires pour l'inventaire |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `inventory` | table \| nil | La table de l'inventaire créé (ou existant), ou nil si la création a échoué. Structure : `{id, label, options, items, type, totalWeight, metadata}` |

### Notes

Champs de `options` :

- `maxWeight` (number, optionnel) : Capacité de poids maximale
- `maxSlots` (number, optionnel) : Nombre maximal d'emplacements
- `columns` (number, optionnel) : Nombre de colonnes pour l'affichage en grille dans l'UI (ex. : 10 emplacements au total mais 2 colonnes → grille de 2x5)
- `temporary` (boolean, optionnel) : Si true, l'inventaire n'est pas sauvegardé en base de données et sera perdu au redémarrage du script
- `prefillItems` (table, optionnel) : Configuration du loot aléatoire. Les objets sont choisis par sélection pondérée sans remise :
  - `minTypes` (number, optionnel) : Nombre minimum de types d'objets différents à ajouter. Par défaut : 1
  - `maxTypes` (number, optionnel) : Nombre maximum de types d'objets différents à ajouter. Par défaut : taille du pool
  - `items` (table, obligatoire) : Tableau des objets possibles, chaque entrée : `{name = string, chance = number, min = number, max = number, metadata = table?}`
- `revealItems` (table, optionnel) : Animation de révélation progressive des objets à l'ouverture de l'inventaire :
  - `delayPerItem` (number, optionnel) : Millisecondes entre chaque révélation d'objet. Par défaut : 1000
  - `randomOrder` (boolean, optionnel) : Si true, les objets sont révélés dans un ordre aléatoire plutôt que par ordre d'emplacement. Par défaut : false
- `slots` (table, optionnel) : Configuration par emplacement. La clé est le numéro d'emplacement, la valeur est une table `SlotConfig` : `label`, `image`, `opacity`, `whitelist`, `blacklist`
- `whitelist` / `blacklist` (table, optionnel) : Filtres d'objets au niveau de l'inventaire. Format : `{itemName = true, ...}`
- `allowedJobs` (table, optionnel) : Jobs autorisés à accéder à cet inventaire
- `allowedIdentifiers` (table, optionnel) : Identifiants de personnage autorisés à accéder à cet inventaire
- `disableIncoming` / `disableOutgoing` (boolean, optionnel) : Bloque les transferts entrants ou sortants effectués par le joueur
- `dropDisabled` (boolean, optionnel) : Si true, les objets ne peuvent pas être déposés depuis cet inventaire
- `noLimitDrag` (boolean, optionnel) : Si true, le glisser-déposer ignore la boîte de dialogue de sélection de quantité et déplace la pile entière. Utilisé en interne pour les shops

Aussi :

- Si `id` existe déjà, l'inventaire existant est renvoyé tel quel, les `items` statiques et `prefillItems` NE sont PAS réappliqués
- `prefillItems` utilise une sélection aléatoire pondérée sans remise (chaque type d'objet ne peut être choisi qu'une seule fois)
- `prefillItems` est traité via `options`, tandis que les `items` statiques sont un paramètre séparé, ils servent des objectifs différents
- Utilise `temporary = true` pour les inventaires éphémères (lootboxes, récompenses d'événements) afin d'éviter de surcharger la base de données
