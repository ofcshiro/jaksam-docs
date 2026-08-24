---
title: "Create building"
description: "Crea un nuevo edificio del lado servidor para agrupar varias puertas bajo reglas de acceso compartidas."
icon: "building"
---

```lua Export
exports["doors_creator"]:createBuilding(buildingData)
```

### Parámetros

| Nombre           | Tipo de dato | Descripción                     |
| -------------- | --------- | ---------------------------------- |
| `buildingData` | table     | Los datos del edificio a añadir       |

### Formato de buildingData

| Field                      | Tipo de dato | Descripción                                            | Required |
| --------------------------- | --------- | -------------------------------------------------------- | -------- |
| `label`                      | string    | Nombre del edificio                                       | Yes      |
| `defaultState`               | integer   | Estado por defecto: 1 = bloqueado, 0 = desbloqueado                    | Yes      |
| `allowedJobs`                | table     | Tabla de jobs con acceso permitido, con grades                | No       |
| `allowedGangs`                | table     | Tabla de gangs con acceso permitido, con grades               | No       |
| `requiredItem`                | string    | Item requerido para el acceso                                     | No       |
| `requiresJobAndItem`          | boolean   | Si es true, se requieren tanto el job como el item                     | No       |
| `requiredCode`                | string    | Código requerido para el acceso                                     | No       |
| `autoClosureSeconds`          | integer   | Segundos tras los cuales las puertas se cierran automáticamente                        | No       |
| `requiresIdentifier`          | boolean   | Si es true, se permiten identifiers específicos                   | No       |
| `allowedIdentifiers`          | table     | Tabla de identifiers con acceso permitido                      | No       |
| `requiredItemRemoveOnUse`     | boolean   | Si es true, el item requerido se eliminará al usarse           | No       |

### Valor de retorno

| Tipo de dato | Descripción                                     |
| --------- | ---------------------------------------------------- |
| integer   | El ID del edificio si tiene éxito, `false` en caso contrario       |

## Ejemplo

```lua
Citizen.CreateThread(function()
    local buildingData = {
        label = "Police Department",
        defaultState = 1, -- 1 = bloqueado, 0 = desbloqueado

        -- Jobs que pueden acceder a este edificio
        allowedJobs = {
            ["police"] = {
                ["0"] = true, -- Recruit
                ["1"] = true, -- Officer
                ["2"] = true, -- Sergeant
                ["3"] = true  -- Lieutenant
            },
            ["sheriff"] = true
        },

        -- Gangs que pueden acceder (solo QB-Core)
        allowedGangs = {
            ["ballas"] = {
                ["3"] = true -- Solo rango de jefe
            }
        },

        -- Item requerido para acceder
        requiredItem = "police_keycard",

        -- Si es true, el jugador necesita tanto el job como el item
        requiresJobAndItem = true,

        -- Código del teclado (si aplica)
        requiredCode = "1234",

        -- Las puertas se cerrarán automáticamente después de esta cantidad de segundos
        autoClosureSeconds = 5,

        -- Identifiers de jugadores individuales que pueden acceder
        requiresIdentifier = true,
        allowedIdentifiers = {
            ["153vav3xxxxxxxxxxxxxxx"] = true,
            ["6ba2f3xxxxxxxxxxxxxxxx"] = true
        },

        -- Eliminar el item de llave cuando se use
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
