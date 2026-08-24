---
title: "Update door"
description: "Actualiza los datos de una puerta existente del lado servidor."
icon: "pen"
---

```lua Export
exports["doors_creator"]:updateDoor(doorId, doorData)
```

### Parámetros

| Nombre       | Tipo de dato | Descripción                     |
| ---------- | --------- | ----------------------------------- |
| `doorId`   | integer   | El ID de la puerta a actualizar           |
| `doorData` | table     | Los datos de la puerta con los que actualizar            |

### Formato de doorData

Este parámetro puede contener cualquiera de los campos usados en `createDoor`. Puedes proporcionar solo los campos que quieres actualizar, ya que la función conservará los valores existentes para los campos no especificados.

| Field                        | Tipo de dato | Descripción                                            |
| ------------------------------ | --------- | -------------------------------------------------------- |
| `label`                          | string    | Nombre de la puerta                                            |
| `defaultState`                   | integer   | Estado por defecto: 1 = bloqueado, 0 = desbloqueado                     |
| `doors`                           | table     | Array de objetos de puerta con modelo y coordenadas             |
| `maxDistance`                     | number    | Distancia máxima para la interacción                              |
| `iconCoords`                      | table     | Coordenadas donde mostrar el icono de interacción                |
| `allowedJobs`                     | table     | Tabla de jobs con acceso permitido, con grades                  |
| `allowedGangs`                    | table     | Tabla de gangs con acceso permitido, con grades                 |
| `requiredItem`                    | string    | Item requerido para el acceso                                       |
| `requiresJobAndItem`              | boolean   | Si es true, se requieren tanto el job como el item                       |
| `requiredCode`                    | string    | Código requerido para el acceso                                       |
| `autoClosureSeconds`              | integer   | Segundos tras los cuales las puertas se cierran automáticamente                          |
| `parentBuilding`                  | integer   | ID del edificio al que pertenece esta puerta                               |
| `isSliding`                       | boolean   | Si es true, la puerta es corredera en lugar de con bisagras                    |
| `displayIcon`                     | boolean   | Si se debe mostrar el icono de interacción                        |
| `requiresIdentifier`              | boolean   | Si es true, se permiten identifiers específicos                      |
| `allowedIdentifiers`              | table     | Tabla de identifiers con acceso permitido                         |
| `vault`                            | table     | Configuración de puerta de caja fuerte                                       |
| `canBeLockpicked`                 | boolean   | Si es true, la puerta se puede abrir con ganzúa                             |
| `alertPoliceOnLockpick`           | boolean   | Si es true, se alerta a la policía cuando se abre la puerta con ganzúa           |
| `soundsData`                       | table     | Configuración de sonidos personalizados                                     |
| `requiredItemRemoveOnUse`         | boolean   | Si es true, el item requerido se eliminará al usarse               |

### Valor de retorno

| Tipo de dato | Descripción                                      |
| --------- | ------------------------------------------------------ |
| boolean   | `true` si la puerta fue actualizada, `false` en caso contrario         |

## Ejemplo

```lua
Citizen.CreateThread(function()
    local doorId = 55

    -- Ejemplo 1: Actualizar solo propiedades específicas
    local doorData = {
        -- Actualizar permisos de acceso
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

        -- Actualizar item requerido
        requiredItem = "special_key",

        -- Cambiar configuración de ganzúa
        canBeLockpicked = true,
        alertPoliceOnLockpick = true
    }

    local success = exports["doors_creator"]:updateDoor(doorId, doorData)

    if success then
        print("Door with ID " .. doorId .. " has been updated")
    else
        print("Failed to update door with ID " .. doorId)
    end

    -- Ejemplo 2: Actualización completa de la puerta
    -- Esto reemplazaría todas las propiedades de la puerta
    local completeUpdate = {
        label = "Updated Door",
        defaultState = 0, -- Ahora desbloqueada por defecto
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
        maxDistance = 3.0, -- Distancia de interacción aumentada
        iconCoords = {
            x = 152.7808,
            y = -1000.5450,
            z = 29.3962
        },
        displayIcon = true,
        isSliding = false,
        parentBuilding = 2, -- Asociación de edificio cambiada
        requiresJobAndItem = false
    }

    -- exports["doors_creator"]:updateDoor(doorId, completeUpdate)
end)
```
