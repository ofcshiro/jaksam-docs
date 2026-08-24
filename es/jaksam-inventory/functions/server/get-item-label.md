---
title: "Get item label"
description: "Obtiene la etiqueta visible de un ítem."
icon: "tag"
---

Obtiene la etiqueta visible de un ítem.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemLabel(itemName)
```

```lua Example
-- Obtiene la etiqueta del ítem
local label = exports['jaksam_inventory']:getItemLabel('bread')
print(label) -- imprime "Bread" o la etiqueta que esté configurada

-- Comprueba si un ítem existe usando la etiqueta (aunque funcionaría, lo mejor sería usar getStaticItem)
if not exports['jaksam_inventory']:getItemLabel('invalid_item') then
    print('Item does not exist')
end
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `itemName` | string | El nombre del ítem del que obtener la etiqueta |

### Valor de retorno

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `label` | string \| nil | La etiqueta visible del ítem, nil si el ítem no existe |
