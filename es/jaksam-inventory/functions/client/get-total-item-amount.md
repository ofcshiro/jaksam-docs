---
title: "Get total item amount"
description: "Obtiene la cantidad total de un ítem específico en el inventario del jugador."
icon: "hashtag"
---

Obtiene la cantidad total de un ítem específico en el inventario del jugador.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getTotalItemAmount(itemName, metadata)
```

```lua Example
-- Obtiene la cantidad total de pan
local breadCount = exports['jaksam_inventory']:getTotalItemAmount('bread')

-- Obtiene la cantidad de un arma específica por número de serie
local weaponCount = exports['jaksam_inventory']:getTotalItemAmount('weapon_pistol', {
    serial = "ABC123"
})
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `itemName` | string | El nombre del ítem a contar |
| `metadata` | table | Metadata con la que comparar al contar (si se proporciona, solo se contarán los ítems con la misma metadata Y el mismo nombre) |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `totalAmount` | number | Cantidad total del ítem en el inventario del jugador |
