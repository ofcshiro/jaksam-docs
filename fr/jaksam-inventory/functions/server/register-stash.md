---
title: "Register stash"
description: "Enregistre dynamiquement une nouvelle stash et crée son inventaire serveur à l'exécution."
icon: "warehouse"
---

Enregistre dynamiquement une nouvelle stash et crée son inventaire serveur à l'exécution.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:registerStash(options)
```

```lua Example
-- Crée une stash publique avec un point d'interaction (runtimeOnly = false)
local stashId = exports['jaksam_inventory']:registerStash({
    label = "Public Storage",
    coords = vector3(100.0, 200.0, 30.0),
    maxWeight = 500,
    maxSlots = 50,
    radius = 5.0,
    runtimeOnly = false -- Active les points d'interaction
})

-- Crée une stash réservée à un job avec un point d'interaction
local policeStashId = exports['jaksam_inventory']:registerStash({
    id = "police_evidence",
    label = "Police Evidence Locker",
    coords = vector3(450.0, -990.0, 30.0),
    maxWeight = 1000,
    maxSlots = 100,
    radius = 3.0,
    allowedJobs = {police = true, sheriff = true},
    runtimeOnly = false -- Active les points d'interaction
})

-- Crée une stash accessible uniquement par code (comportement par défaut, runtimeOnly = true)
-- Les joueurs ne peuvent pas y accéder via une interaction dans le monde, uniquement via le code
local hiddenStashId = exports['jaksam_inventory']:registerStash({
    id = "secret_stash",
    label = "Secret Storage",
    maxWeight = 200,
    maxSlots = 30
    -- Aucune coordonnée fournie, accessible uniquement par le code
})

-- Crée une stash privée (chaque joueur obtient son propre inventaire en accédant à la stash)
local privateStashId = exports['jaksam_inventory']:registerStash({
    id = "luxury_apartment_stash",
    label = "Personal Safe",
    coords = vector3(300.0, 400.0, 50.0),
    maxWeight = 200,
    maxSlots = 30,
    isPrivate = true
})

-- Crée une stash temporaire avec des objets de départ (ne sera pas sauvegardée en base de données)
local tempStashId = exports['jaksam_inventory']:registerStash({
    label = "Event Loot Box",
    coords = vector3(500.0, 600.0, 20.0),
    maxWeight = 100,
    maxSlots = 20,
    temporary = true,
    startingItems = {
        {"bread", 5, nil},
        {"water", 3, nil},
        {"money", 1000, nil}
    }
})

-- Crée une stash basée sur un menu (runtimeOnly = true par défaut)
-- Utile pour les systèmes de menu/UI personnalisés
local virtualStashId = exports['jaksam_inventory']:registerStash({
    id = "player_bank_vault",
    label = "Bank Vault",
    maxWeight = 500,
    maxSlots = 50,
    isPrivate = true
    -- runtimeOnly = true par défaut, accessible uniquement par le code
})

-- Ouvre la stash par code depuis le serveur (ex. : depuis un menu ou une commande)
RegisterCommand('openvault', function(source)
    local charId = Framework.getPlayerCharIdentifier(source)
    local stashId = "player_bank_vault_" .. charId
    exports['jaksam_inventory']:forceOpenInventory(source, stashId)
end)

-- Alternative : Ouvrir depuis un script côté client
-- exports['jaksam_inventory']:openInventory('stashId')
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `options` | table | Table de configuration de la stash (voir les Notes ci-dessous) |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `stashId` | string \| nil | L'ID de la stash créée, nil si la création a échoué |

### Notes

Champs de `options` :

- `id` (string, optionnel) : ID unique de la stash. Si non fourni, un ID sera généré automatiquement
- `label` (string, obligatoire) : Nom affiché de la stash
- `coords` (vector3 \| table, optionnel) : Emplacement où la stash peut être accédée via un point d'interaction
- `maxWeight` (number, optionnel) : Capacité de poids maximale. Par défaut : 100
- `maxSlots` (number, optionnel) : Nombre maximal d'emplacements. Par défaut : 100
- `radius` (number, optionnel) : Distance à partir de laquelle les joueurs peuvent accéder à la stash. Par défaut : 3.0
- `isPrivate` (boolean, optionnel) : Si true, crée un inventaire séparé pour chaque joueur. Par défaut : false
- `allowedJobs` (table, optionnel) : Table des noms de jobs pouvant accéder à la stash. Si nil, la stash est publique
- `temporary` (boolean, optionnel) : Si true, la stash ne sera pas sauvegardée en base de données et sera perdue au redémarrage du script. Par défaut : false
- `startingItems` (table, optionnel) : Objets à ajouter à la première création de la stash. Format : `{{itemName, amount, metadata}, ...}`
- `runtimeOnly` (boolean, optionnel) : Si true (par défaut), la stash ne peut être ouverte que par code. Si false et que des coordonnées sont fournies, crée des points d'interaction côté client. Par défaut : true
