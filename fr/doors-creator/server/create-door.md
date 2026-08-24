---
title: "Create door"
description: "Crée une nouvelle porte côté serveur avec un contrôle complet sur les règles d'accès et le comportement."
icon: "square-plus"
---

```lua Export
exports["doors_creator"]:createDoor(doorData)
```

### Paramètres

| Nom       | Type de donnée | Description                  |
| ---------- | --------- | ---------------------------- |
| `doorData` | table     | Les données de la porte à ajouter     |

### Format de doorData

| Champ                        | Type de donnée | Description                                            | Requis |
| ------------------------------ | --------- | -------------------------------------------------------- | -------- |
| `label`                         | string    | Nom de la porte                                            | Oui      |
| `defaultState`                  | integer   | État par défaut : 1 = verrouillé, 0 = déverrouillé                     | Oui      |
| `doors`                          | table     | Tableau d'objets porte avec modèle et coordonnées             | Oui      |
| `maxDistance`                    | number    | Distance maximale pour l'interaction                              | Oui      |
| `iconCoords`                     | table     | Coordonnées où afficher l'icône d'interaction                | Oui      |
| `allowedJobs`                    | table     | Table des jobs autorisés à accéder, avec les grades                  | Non       |
| `allowedGangs`                   | table     | Table des gangs autorisés à accéder, avec les grades                 | Non       |
| `requiredItem`                   | string    | Item requis pour accéder                                       | Non       |
| `requiresJobAndItem`             | boolean   | Si true, le job et l'item sont tous les deux requis                       | Non       |
| `requiredCode`                   | string    | Code requis pour accéder                                       | Non       |
| `autoClosureSeconds`             | integer   | Secondes après lesquelles les portes se referment automatiquement                          | Non       |
| `parentBuilding`                 | integer   | L'ID du bâtiment auquel cette porte appartient                               | Non       |
| `isSliding`                      | boolean   | Si true, la porte est coulissante plutôt qu'à charnières                    | Non       |
| `displayIcon`                    | boolean   | Indique si l'icône d'interaction doit être affichée                        | Non       |
| `requiresIdentifier`             | boolean   | Si true, des identifiants spécifiques sont autorisés                      | Non       |
| `allowedIdentifiers`             | table     | Table des identifiants autorisés à accéder                         | Non       |
| `vault`                           | table     | Configuration de la porte de coffre                                       | Non       |
| `canBeLockpicked`                | boolean   | Si true, la porte peut être crochetée                             | Non       |
| `alertPoliceOnLockpick`          | boolean   | Si true, la police est alertée quand la porte est crochetée           | Non       |
| `soundsData`                      | table     | Configuration des sons personnalisés                                     | Non       |
| `requiredItemRemoveOnUse`        | boolean   | Si true, l'item requis sera retiré à l'utilisation               | Non       |

### Valeur de retour

| Type de donnée | Description                                    |
| --------- | --------------------------------------------------- |
| boolean   | `true` si la porte a été ajoutée, `false` sinon       |

## Exemple

```lua
Citizen.CreateThread(function()
    local doorData = {
        label = "Police Front Door",
        defaultState = 1, -- 1 = locked, 0 = unlocked

        -- Array of physical door objects
        doors = {
            {
                model = 747286790, -- Hash of the door model
                coords = {
                    x = 152.7808,
                    y = -1000.5450,
                    z = 29.3962
                }
            },
            -- You can add a second door for double doors
            {
                model = 747286791,
                coords = {
                    x = 154.8200,
                    y = -1000.5450,
                    z = 29.3962
                }
            }
        },

        -- Maximum distance for interaction
        maxDistance = 2.0,

        -- Where to show the interaction icon
        iconCoords = {
            x = 153.7808,
            y = -1000.5450,
            z = 29.3962
        },

        -- Jobs that can access this door
        allowedJobs = {
            ["police"] = {
                ["0"] = true, -- Recruit
                ["1"] = true, -- Officer
                ["2"] = true  -- Sergeant
            },

            ["ambulance"] = true
        },

        -- Gangs that can access (QB-Core only)
        allowedGangs = {
            ["ballas"] = {
                ["2"] = true, -- Only higher ranks
                ["3"] = true
            }
        },

        -- Item required to access
        requiredItem = "police_keycard",

        -- If true, player needs both the job AND the item
        requiresJobAndItem = false,

        -- Building this door belongs to
        parentBuilding = 1,

        -- If it's a sliding door
        isSliding = false,

        -- Whether to display the interaction icon
        displayIcon = true,

        -- Door can be lockpicked
        canBeLockpicked = true,

        -- Alert police when lockpicked
        alertPoliceOnLockpick = true,

        -- Custom sounds
        soundsData = {
            lockSound = "fence",
            unlockSound = "fence"
        }
    }

    local success = exports["doors_creator"]:createDoor(doorData)

    if success then
        print("Door created successfully")
    else
        print("Failed to create door")
    end
end)
```
