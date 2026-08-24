---
title: "Get item image path"
description: "Obtiene la ruta de imagen NUI de un ítem, con una imagen predeterminada de respaldo si no se encuentra ninguna."
icon: "image"
---

Obtiene la ruta de imagen NUI de un ítem. La función usa un sistema de respaldo: primero comprueba si el ítem tiene un campo `image` personalizado, luego intenta encontrar archivos `.png` o `.webp`, y finalmente recurre a la imagen predeterminada `box.webp`.

<CodeGroup>

```lua Export
exports['jaksam_inventory']:getItemImagePath(itemName)
```

```lua Example
local imagePath = exports['jaksam_inventory']:getItemImagePath('bread')
print(imagePath) -- nui://jaksam_inventory/_images/bread.png

-- Ítem con campo de imagen personalizado
local customImage = exports['jaksam_inventory']:getItemImagePath('custom_item')
print(customImage) -- nui://jaksam_inventory/_images/custom_image.png (si item.image está configurado)

-- Ítem no encontrado devuelve la imagen predeterminada
local notFound = exports['jaksam_inventory']:getItemImagePath('invalid_item')
print(notFound) -- nui://jaksam_inventory/_images/box.webp
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de Dato | Descripción |
| --- | --- | --- |
| `itemName` | string | El nombre del ítem del que se quiere obtener la ruta de imagen |

### Valor de retorno

| Nombre | Tipo de Dato | Descripción |
| --- | --- | --- |
| `imagePath` | string | La ruta de imagen NUI (p. ej., "nui://jaksam_inventory/_images/bread.png"). Siempre devuelve una ruta válida, recurriendo a `box.webp` si el ítem no existe o no se encuentra ninguna imagen |
