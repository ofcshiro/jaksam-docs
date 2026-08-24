---
title: "Is inventory open"
description: "Comprueba si un inventario está actualmente abierto."
icon: "door-open"
---

Comprueba si un inventario está actualmente abierto. Si no se proporciona ningún ID de inventario, devuelve si la interfaz del inventario está actualmente activa (algún inventario abierto). Si se proporciona un ID de inventario, comprueba si ese inventario específico está abierto.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:isInventoryOpen(inventoryId)
```

```lua Example
-- Comprueba si hay alguna interfaz de inventario abierta
local isAnyInventoryOpen = exports['jaksam_inventory']:isInventoryOpen()

if isAnyInventoryOpen then
    print('An inventory is currently open')
else
    print('No inventory is open')
end

-- Comprueba si un inventario específico está abierto
local isPoliceStashOpen = exports['jaksam_inventory']:isInventoryOpen('police_stash_1')

if isPoliceStashOpen then
    print('Police stash is currently open')
end

-- Evita abrir otra interfaz si el inventario ya está abierto
if not exports['jaksam_inventory']:isInventoryOpen() then
    -- Abre la interfaz personalizada
    TriggerEvent('myScript:openCustomUI')
else
    notify("Can't do it while inventory is open")
end
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| nil | El ID del inventario a comprobar. Si es nil, devuelve si alguna interfaz de inventario está actualmente activa |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `isOpen` | boolean | True si el inventario (o cualquier interfaz de inventario cuando inventoryId es nil) está abierto, false en caso contrario |
