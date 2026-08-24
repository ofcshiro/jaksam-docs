---
title: "Get total item amount"
description: "Devuelve la cantidad total de un ítem específico en un inventario, incluyendo ítems dentro de contenedores."
icon: "hashtag"
---

Devuelve la cantidad total de un ítem específico en un inventario, incluyendo ítems dentro de contenedores.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getTotalItemAmount(inventoryId, itemName, metadata, skipContainers)
```

```lua Example
-- Obtiene la cantidad total de pan en el inventario
local total = exports['jaksam_inventory']:getTotalItemAmount(1, 'bread')

-- Obtiene la cantidad con metadata específica
local total = exports['jaksam_inventory']:getTotalItemAmount(1, 'weapon_pistol', {
    serial = "ABC123"
})

-- Obtiene la cantidad excluyendo contenedores
local total, totalNoContainers = exports['jaksam_inventory']:getTotalItemAmount(1, 'bread', nil, true)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| number | El ID del inventario a comprobar |
| `itemName` | string | El nombre del ítem a contar |
| `metadata` | table | Metadata con la que comparar al contar (si se proporciona, solo se contarán los ítems con la misma metadata Y el mismo nombre) |
| `skipContainers` | boolean | Si es true, los ítems dentro de contenedores no se contarán |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `totalAmount` | number | Cantidad total del ítem en el inventario, incluyendo contenedores (solo si skipContainers es false) |
| `totalAmountContainersExcluded` | number \| nil | Cantidad total excluyendo contenedores (solo si skipContainers es false) |
