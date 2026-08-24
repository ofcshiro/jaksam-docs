---
title: "Set item metadata in slot"
description: "Actualiza la metadata de un ítem en un slot específico del inventario."
icon: "grid-2"
---

Actualiza la metadata de un ítem en un slot específico del inventario.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:setItemMetadataInSlot(inventoryId, slotId, metadata)
```

```lua Example
-- Actualiza la munición del arma
exports['jaksam_inventory']:setItemMetadataInSlot(1, 5, {
    serial = "ABC123",
    ammo = 6 -- actualiza la cantidad de munición
})

-- Actualiza la durabilidad del ítem
exports['jaksam_inventory']:setItemMetadataInSlot(1, 3, {
    durability = 50
})
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `inventoryId` | string \| number | El ID del inventario que contiene el ítem |
| `slotId` | number | El slot que contiene el ítem a actualizar |
| `metadata` | table | La nueva metadata a establecer |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `success` | boolean | True si la metadata se actualizó correctamente |
| `resultCode` | string | Mensaje de error si la operación falló |
