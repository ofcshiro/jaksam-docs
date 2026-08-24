---
title: "Register stash"
description: "Registra dinámicamente un nuevo stash y crea su inventario de servidor en tiempo de ejecución."
icon: "warehouse"
---

Registra dinámicamente un nuevo stash y crea su inventario de servidor en tiempo de ejecución.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:registerStash(options)
```

```lua Example
-- Crea un stash público con punto de interacción (runtimeOnly = false)
local stashId = exports['jaksam_inventory']:registerStash({
    label = "Public Storage",
    coords = vector3(100.0, 200.0, 30.0),
    maxWeight = 500,
    maxSlots = 50,
    radius = 5.0,
    runtimeOnly = false -- Habilita puntos de interacción
})

-- Crea un stash restringido por trabajo con punto de interacción
local policeStashId = exports['jaksam_inventory']:registerStash({
    id = "police_evidence",
    label = "Police Evidence Locker",
    coords = vector3(450.0, -990.0, 30.0),
    maxWeight = 1000,
    maxSlots = 100,
    radius = 3.0,
    allowedJobs = {police = true, sheriff = true},
    runtimeOnly = false -- Habilita puntos de interacción
})

-- Crea un stash solo programático (comportamiento por defecto, runtimeOnly = true)
-- Los jugadores no pueden acceder a él mediante interacción en el mundo, solo a través de código
local hiddenStashId = exports['jaksam_inventory']:registerStash({
    id = "secret_stash",
    label = "Secret Storage",
    maxWeight = 200,
    maxSlots = 30
    -- No se proporcionan coords, se accede solo de forma programática
})

-- Crea un stash privado (cada jugador obtiene su propio inventario al acceder al stash)
local privateStashId = exports['jaksam_inventory']:registerStash({
    id = "luxury_apartment_stash",
    label = "Personal Safe",
    coords = vector3(300.0, 400.0, 50.0),
    maxWeight = 200,
    maxSlots = 30,
    isPrivate = true
})

-- Crea un stash temporal con ítems iniciales (no se guardará en la base de datos)
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

-- Crea un stash basado en menú (runtimeOnly = true por defecto)
-- Útil para sistemas de menús/interfaces personalizadas
local virtualStashId = exports['jaksam_inventory']:registerStash({
    id = "player_bank_vault",
    label = "Bank Vault",
    maxWeight = 500,
    maxSlots = 50,
    isPrivate = true
    -- runtimeOnly = true por defecto, se accede solo de forma programática
})

-- Abre el stash de forma programática desde el servidor (por ejemplo, desde un menú o comando)
RegisterCommand('openvault', function(source)
    local charId = Framework.getPlayerCharIdentifier(source)
    local stashId = "player_bank_vault_" .. charId
    exports['jaksam_inventory']:forceOpenInventory(source, stashId)
end)

-- Alternativa: Abrir desde un script del lado del cliente
-- exports['jaksam_inventory']:openInventory('stashId')
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `options` | table | Tabla de configuración para el stash (ver Notas más abajo) |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `stashId` | string \| nil | El ID del stash creado, nil si la creación falló |

### Notas

Campos de `options`:

- `id` (string, opcional): ID único para el stash. Si no se proporciona, se generará uno automáticamente
- `label` (string, obligatorio): Nombre visible del stash
- `coords` (vector3 \| table, opcional): Ubicación donde se puede acceder al stash mediante un punto de interacción
- `maxWeight` (number, opcional): Capacidad máxima de peso. Por defecto: 100
- `maxSlots` (number, opcional): Número máximo de slots. Por defecto: 100
- `radius` (number, opcional): Distancia desde la que los jugadores pueden acceder al stash. Por defecto: 3.0
- `isPrivate` (boolean, opcional): Si es true, crea un inventario separado para cada jugador. Por defecto: false
- `allowedJobs` (table, opcional): Tabla de nombres de trabajos que pueden acceder al stash. Si es nil, el stash es público
- `temporary` (boolean, opcional): Si es true, el stash no se guardará en la base de datos y se perderá al reiniciar el script. Por defecto: false
- `startingItems` (table, opcional): Ítems a añadir cuando el stash se crea por primera vez. Formato: `{{itemName, amount, metadata}, ...}`
- `runtimeOnly` (boolean, opcional): Si es true (por defecto), el stash solo se puede abrir de forma programática. Si es false y se proporcionan coords, crea puntos de interacción en el cliente. Por defecto: true
