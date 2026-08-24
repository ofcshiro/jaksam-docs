---
title: "Update door"
description: "Met à jour les données d'une porte existante côté serveur."
icon: "pen"
---

```lua Export
exports["doors_creator"]:updateDoor(doorId, doorData)
```

### Paramètres

| Nom       | Type de donnée | Description                     |
| ---------- | --------- | ----------------------------------- |
| `doorId`   | integer   | L'ID de la porte à mettre à jour           |
| `doorData` | table     | Les données de la porte à mettre à jour            |

### Format de doorData

Ce paramètre peut contenir n'importe lequel des champs utilisés dans `createDoor`. Tu peux fournir uniquement les champs que tu souhaites mettre à jour, la fonction conservera les valeurs existantes pour les champs non spécifiés.

| Champ                        | Type de donnée | Description                                            |
| ------------------------------ | --------- | -------------------------------------------------------- |
| `label`                          | string    | Nom de la porte                                            |
| `defaultState`                   | integer   | État par défaut : 1 = verrouillé, 0 = déverrouillé                     |
| `doors`                           | table     | Tableau d'objets porte avec modèle et coordonnées             |
| `maxDistance`                     | number    | Distance maximale pour l'interaction                              |
| `iconCoords`                      | table     | Coordonnées où afficher l'icône d'interaction                |
| `allowedJobs`                     | table     | Table des jobs autorisés à accéder, avec les grades                  |
| `allowedGangs`                    | table     | Table des gangs autorisés à accéder, avec les grades                 |
| `requiredItem`                    | string    | Item requis pour accéder                                       |
| `requiresJobAndItem`              | boolean   | Si true, le job et l'item sont tous les deux requis                       |
| `requiredCode`                    | string    | Code requis pour accéder                                       |
| `autoClosureSeconds`              | integer   | Secondes après lesquelles les portes se referment automatiquement                          |
| `parentBuilding`                  | integer   | L'ID du bâtiment auquel cette porte appartient                               |
| `isSliding`                       | boolean   | Si true, la porte est coulissante plutôt qu'à charnières                    |
| `displayIcon`                     | boolean   | Indique si l'icône d'interaction doit être affichée                        |
| `requiresIdentifier`              | boolean   | Si true, des identifiants spécifiques sont autorisés                      |
| `allowedIdentifiers`              | table     | Table des identifiants autorisés à accéder                         |
| `vault`                            | table     | Configuration de la porte de coffre                                       |
| `canBeLockpicked`                 | boolean   | Si true, la porte peut être crochetée                             |
| `alertPoliceOnLockpick`           | boolean   | Si true, la police est alertée quand la porte est crochetée           |
| `soundsData`                       | table     | Configuration des sons personnalisés                                     |
| `requiredItemRemoveOnUse`         | boolean   | Si true, l'item requis sera retiré à l'utilisation               |

### Valeur de retour

| Type de donnée | Description                                      |
| --------- | ------------------------------------------------------ |
| boolean   | `true` si la porte a été mise à jour, `false` sinon         |

## Exemple

```lua
Citizen.CreateThread(function()
    local doorId = 55

    -- Example 1: Update only specific properties
    local doorData = {
        -- Update access permissions
        allowedIdentifiers = {
            ["steam:1100001xxxxxxxx"] = true,
            ["license:xxxxxxxxxxxxxxx"] = true
        },
        allowedJobs = {
            ["police"] = {
                ["0"] = true,
                ["1"] = true,
                ["2"] = true
            }
        },

        -- Update required item
        requiredItem = "special_key",

        -- Change lockpick settings
        canBeLockpicked = true,
        alertPoliceOnLockpick = true
    }

    local success = exports["doors_creator"]:updateDoor(doorId, doorData)

    if success then
        print("Door with ID " .. doorId .. " has been updated")
    else
        print("Failed to update door with ID " .. doorId)
    end

    -- Example 2: Complete door update
    -- This would replace all properties of the door
    local completeUpdate = {
        label = "Updated Door",
        defaultState = 0, -- Now unlocked by default
        doors = {
            {
                model = 747286790,
                coords = {
                    x = 152.7808,
                    y = -1000.5450,
                    z = 29.3962
                }
            }
        },
        maxDistance = 3.0, -- Increased interaction distance
        iconCoords = {
            x = 152.7808,
            y = -1000.5450,
            z = 29.3962
        },
        displayIcon = true,
        isSliding = false,
        parentBuilding = 2, -- Changed building association
        requiresJobAndItem = false
    }

    -- exports["doors_creator"]:updateDoor(doorId, completeUpdate)
end)
```
