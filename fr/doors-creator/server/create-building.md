---
title: "Create building"
description: "Crée un nouveau bâtiment côté serveur pour regrouper plusieurs portes sous des règles d'accès partagées."
icon: "building"
---

```lua Export
exports["doors_creator"]:createBuilding(buildingData)
```

### Paramètres

| Nom           | Type de donnée | Description                     |
| -------------- | --------- | ---------------------------------- |
| `buildingData` | table     | Les données du bâtiment à ajouter       |

### Format de buildingData

| Champ                      | Type de donnée | Description                                            | Requis |
| --------------------------- | --------- | -------------------------------------------------------- | -------- |
| `label`                      | string    | Nom du bâtiment                                       | Oui      |
| `defaultState`               | integer   | État par défaut : 1 = verrouillé, 0 = déverrouillé                    | Oui      |
| `allowedJobs`                | table     | Table des jobs autorisés à accéder, avec les grades                | Non       |
| `allowedGangs`                | table     | Table des gangs autorisés à accéder, avec les grades               | Non       |
| `requiredItem`                | string    | Item requis pour accéder                                     | Non       |
| `requiresJobAndItem`          | boolean   | Si true, le job et l'item sont tous les deux requis                     | Non       |
| `requiredCode`                | string    | Code requis pour accéder                                     | Non       |
| `autoClosureSeconds`          | integer   | Secondes après lesquelles les portes se referment automatiquement                        | Non       |
| `requiresIdentifier`          | boolean   | Si true, des identifiants spécifiques sont autorisés                   | Non       |
| `allowedIdentifiers`          | table     | Table des identifiants autorisés à accéder                      | Non       |
| `requiredItemRemoveOnUse`     | boolean   | Si true, l'item requis sera retiré à l'utilisation           | Non       |

### Valeur de retour

| Type de donnée | Description                                     |
| --------- | ---------------------------------------------------- |
| integer   | L'ID du bâtiment en cas de succès, `false` sinon       |

## Exemple

```lua
Citizen.CreateThread(function()
    local buildingData = {
        label = "Police Department",
        defaultState = 1, -- 1 = locked, 0 = unlocked

        -- Jobs that can access this building
        allowedJobs = {
            ["police"] = {
                ["0"] = true, -- Recruit
                ["1"] = true, -- Officer
                ["2"] = true, -- Sergeant
                ["3"] = true  -- Lieutenant
            },
            ["sheriff"] = true
        },

        -- Gangs that can access (QB-Core only)
        allowedGangs = {
            ["ballas"] = {
                ["3"] = true -- Only boss rank
            }
        },

        -- Item required to access
        requiredItem = "police_keycard",

        -- If true, player needs both the job AND the item
        requiresJobAndItem = true,

        -- Keypad code (if applicable)
        requiredCode = "1234",

        -- Doors will auto-close after this many seconds
        autoClosureSeconds = 5,

        -- Individual player identifiers that can access
        requiresIdentifier = true,
        allowedIdentifiers = {
            ["153vav3xxxxxxxxxxxxxxx"] = true,
            ["6ba2f3xxxxxxxxxxxxxxxx"] = true
        },

        -- Remove the key item when used
        requiredItemRemoveOnUse = false
    }

    local buildingId = exports["doors_creator"]:createBuilding(buildingData)

    if buildingId then
        print("Building created with ID: " .. buildingId)
    else
        print("Failed to create building")
    end
end)
```
