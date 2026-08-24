---
title: "Create inventory"
description: "Crea un nuevo inventario tanto en la base de datos como en memoria (según las opciones)."
icon: "square-plus"
---

Crea un nuevo inventario tanto en la base de datos como en memoria (según las opciones). Si ya existe un inventario con el mismo ID, devuelve el existente sin modificarlo.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:createInventory(id, label, options, items, inventoryType, metadata)
```

```lua Example
-- Ejemplo: Crea una caja de botín con loot dinámico según la rareza
-- No olvides asegurar el evento de alguna forma según tu caso de uso, de lo contrario los tramposos podrían simplemente disparar el evento para obtener botín gratis
RegisterNetEvent('myresource:openLootCrate', function(rarity)
    local playerId = source

    -- Define los pools de loot según la rareza
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
        nil, -- Genera el ID automáticamente
        "Loot Crate (" .. rarity .. ")", -- Etiqueta dinámica
        {
            temporary = true, -- El inventario se perderá al reiniciar el script
            maxSlots = 5,
            maxWeight = 50.0,
            disableIncoming = true, -- El jugador no puede añadir ítems a este inventario
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

    -- Abre la interfaz del inventario para el jugador
    if inventory then
        exports['jaksam_inventory']:forceOpenInventory(playerId, inventory.id)
    end
end)
```

```lua Example: persistent stash
-- Crea un stash persistente con ítems iniciales fijos
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

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `id` | string \| nil | Identificador único para el inventario. Si es nil, se genera un ID aleatorio |
| `label` | string \| nil | Nombre visible del inventario. Si es nil, se usará una traducción basada en el tipo de inventario |
| `options` | table | Opciones de configuración para el inventario (ver Notas más abajo) |
| `items` | table | Ítems estáticos a añadir cuando el inventario se crea por primera vez. Formato array: `{{itemName, amount, metadata}, ...}`. Se ignora si el inventario ya existe en la base de datos |
| `inventoryType` | string | Tipo de inventario. Por defecto: "stash". Otros valores: "player", "trunk", "glovebox" |
| `metadata` | table | Metadata adicional para el inventario |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventory` | table \| nil | La tabla del inventario creado (o existente), o nil si la creación falló. Estructura: `{id, label, options, items, type, totalWeight, metadata}` |

### Notas

Campos de `options`:

- `maxWeight` (number, opcional): Capacidad máxima de peso
- `maxSlots` (number, opcional): Número máximo de slots
- `columns` (number, opcional): Número de columnas para la vista en cuadrícula en la interfaz (por ejemplo, 10 slots totales pero 2 columnas → cuadrícula de 2x5)
- `temporary` (boolean, opcional): Si es true, el inventario no se guarda en la base de datos y se perderá al reiniciar el script
- `prefillItems` (table, opcional): Configuración de loot aleatorio. Los ítems se eligen mediante selección ponderada sin repetición:
  - `minTypes` (number, opcional): Número mínimo de tipos de ítems distintos a añadir. Por defecto: 1
  - `maxTypes` (number, opcional): Número máximo de tipos de ítems distintos a añadir. Por defecto: tamaño del pool
  - `items` (table, obligatorio): Array de posibles ítems, cada entrada: `{name = string, chance = number, min = number, max = number, metadata = table?}`
- `revealItems` (table, opcional): Animación de revelado progresivo de ítems al abrir el inventario:
  - `delayPerItem` (number, opcional): Milisegundos entre cada revelado de ítem. Por defecto: 1000
  - `randomOrder` (boolean, opcional): Si es true, los ítems se revelan en orden aleatorio en lugar de por orden de slot. Por defecto: false
- `slots` (table, opcional): Configuración por slot. La clave es el número de slot, el valor es una tabla `SlotConfig`: `label`, `image`, `opacity`, `whitelist`, `blacklist`
- `whitelist` / `blacklist` (table, opcional): Filtros de ítems a nivel de inventario. Formato: `{itemName = true, ...}`
- `allowedJobs` (table, opcional): Trabajos con permiso para acceder a este inventario
- `allowedIdentifiers` (table, opcional): Identificadores de personaje con permiso para acceder a este inventario
- `disableIncoming` / `disableOutgoing` (boolean, opcional): Bloquea las transferencias de entrada o salida por parte del jugador
- `dropDisabled` (boolean, opcional): Si es true, los ítems no se pueden soltar desde este inventario
- `noLimitDrag` (boolean, opcional): Si es true, arrastrar ignora el diálogo de selección de cantidad y mueve la pila completa. Se usa internamente para tiendas

Además:

- Si `id` ya existe, se devuelve el inventario existente tal cual, los `items` estáticos y `prefillItems` NO se vuelven a aplicar
- `prefillItems` usa selección aleatoria ponderada sin repetición (cada tipo de ítem solo se puede elegir una vez)
- `prefillItems` se procesa a través de `options`, mientras que los `items` estáticos son un parámetro separado; sirven para propósitos distintos
- Usa `temporary = true` para inventarios efímeros (lootboxes, recompensas de eventos) y así evitar que la base de datos crezca innecesariamente
