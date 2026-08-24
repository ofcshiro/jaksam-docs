---
title: "Create door"
description: "Crea una nueva puerta del lado servidor con control total sobre las reglas de acceso y el comportamiento."
icon: "square-plus"
---

```lua Export
exports["doors_creator"]:createDoor(doorData)
```

### Parámetros

| Nombre       | Tipo de dato | Descripción                  |
| ---------- | --------- | ---------------------------- |
| `doorData` | table     | Los datos de la puerta a añadir     |

### Formato de doorData

| Field                        | Tipo de dato | Descripción                                            | Required |
| ------------------------------ | --------- | -------------------------------------------------------- | -------- |
| `label`                         | string    | Nombre de la puerta                                            | Yes      |
| `defaultState`                  | integer   | Estado por defecto: 1 = bloqueado, 0 = desbloqueado                     | Yes      |
| `doors`                          | table     | Array de objetos de puerta con modelo y coordenadas             | Yes      |
| `maxDistance`                    | number    | Distancia máxima para la interacción                              | Yes      |
| `iconCoords`                     | table     | Coordenadas donde mostrar el icono de interacción                | Yes      |
| `allowedJobs`                    | table     | Tabla de jobs con acceso permitido, con grades                  | No       |
| `allowedGangs`                   | table     | Tabla de gangs con acceso permitido, con grades                 | No       |
| `requiredItem`                   | string    | Item requerido para el acceso                                       | No       |
| `requiresJobAndItem`             | boolean   | Si es true, se requieren tanto el job como el item                       | No       |
| `requiredCode`                   | string    | Código requerido para el acceso                                       | No       |
| `autoClosureSeconds`             | integer   | Segundos tras los cuales las puertas se cierran automáticamente                          | No       |
| `parentBuilding`                 | integer   | ID del edificio al que pertenece esta puerta                               | No       |
| `isSliding`                      | boolean   | Si es true, la puerta es corredera en lugar de con bisagras                    | No       |
| `displayIcon`                    | boolean   | Si se debe mostrar el icono de interacción                        | No       |
| `requiresIdentifier`             | boolean   | Si es true, se permiten identifiers específicos                      | No       |
| `allowedIdentifiers`             | table     | Tabla de identifiers con acceso permitido                         | No       |
| `vault`                           | table     | Configuración de puerta de caja fuerte                                       | No       |
| `canBeLockpicked`                | boolean   | Si es true, la puerta se puede abrir con ganzúa                             | No       |
| `alertPoliceOnLockpick`          | boolean   | Si es true, se alerta a la policía cuando se abre la puerta con ganzúa           | No       |
| `soundsData`                      | table     | Configuración de sonidos personalizados                                     | No       |
| `requiredItemRemoveOnUse`        | boolean   | Si es true, el item requerido se eliminará al usarse               | No       |

### Valor de retorno

| Tipo de dato | Descripción                                    |
| --------- | --------------------------------------------------- |
| boolean   | `true` si la puerta fue añadida, `false` en caso contrario       |

## Ejemplo

```lua
Citizen.CreateThread(function()
    local doorData = {
        label = "Police Front Door",
        defaultState = 1, -- 1 = bloqueado, 0 = desbloqueado

        -- Array de objetos de puerta físicos
        doors = {
            {
                model = 747286790, -- Hash del modelo de la puerta
                coords = {
                    x = 152.7808,
                    y = -1000.5450,
                    z = 29.3962
                }
            },
            -- Puedes añadir una segunda puerta para puertas dobles
            {
                model = 747286791,
                coords = {
                    x = 154.8200,
                    y = -1000.5450,
                    z = 29.3962
                }
            }
        },

        -- Distancia máxima para la interacción
        maxDistance = 2.0,

        -- Dónde mostrar el icono de interacción
        iconCoords = {
            x = 153.7808,
            y = -1000.5450,
            z = 29.3962
        },

        -- Jobs que pueden acceder a esta puerta
        allowedJobs = {
            ["police"] = {
                ["0"] = true, -- Recruit
                ["1"] = true, -- Officer
                ["2"] = true  -- Sergeant
            },

            ["ambulance"] = true
        },

        -- Gangs que pueden acceder (solo QB-Core)
        allowedGangs = {
            ["ballas"] = {
                ["2"] = true, -- Solo rangos superiores
                ["3"] = true
            }
        },

        -- Item requerido para acceder
        requiredItem = "police_keycard",

        -- Si es true, el jugador necesita tanto el job como el item
        requiresJobAndItem = false,

        -- Edificio al que pertenece esta puerta
        parentBuilding = 1,

        -- Si es una puerta corredera
        isSliding = false,

        -- Si se debe mostrar el icono de interacción
        displayIcon = true,

        -- La puerta se puede abrir con ganzúa
        canBeLockpicked = true,

        -- Alertar a la policía cuando se abre con ganzúa
        alertPoliceOnLockpick = true,

        -- Sonidos personalizados
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
