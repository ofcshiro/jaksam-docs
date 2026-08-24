---
title: "Get item label"
description: "Obtiene solo el label (nombre para mostrar) de un ítem. Una alternativa más simple y rápida a getStaticItem cuando solo necesitas el label del ítem."
icon: "tag"
---

Obtiene solo el label (nombre para mostrar) de un ítem. Esta es una alternativa más simple y rápida a `getStaticItem` cuando solo necesitas el label del ítem.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemLabel(itemName)
```

```lua Example
local label = exports['jaksam_inventory']:getItemLabel('bread')
print(label) -- Bread

-- Ítem no encontrado devuelve nil
local notFound = exports['jaksam_inventory']:getItemLabel('invalid_item')
print(notFound) -- nil
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de Dato | Descripción |
| --- | --- | --- |
| `itemName` | string | El nombre del ítem del que se quiere obtener el label |

### Valor de retorno

| Nombre | Tipo de Dato | Descripción |
| --- | --- | --- |
| `label` | string \| nil | El label (nombre para mostrar) del ítem, o nil si el ítem no se encuentra |
