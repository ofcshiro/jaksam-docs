---
title: "Cambiar el icono de las puertas"
description: "Personaliza el color, la imagen y el tamaño del icono de interacción de la puerta."
icon: "icons"
---

## Cómo cambiar el color

Para cambiar los colores del icono, edita el archivo `doors_creator/integrations/cl_integrations.lua` y edita las líneas sobre el color:

```lua
-- r = rojo, g = verde, b = azul, a = opacidad
-- Todos los valores van de 0 a 255
-- Si todos los colores están en 255, la imagen tendrá el color predeterminado
color = {
    r = 50,
    g = 255,
    b = 50,
    a = 255,
}
```

## Cómo cambiar el icono/imagen

Para cambiar el icono/imagen, simplemente reemplaza las imágenes en la carpeta `doors_creator/icons/` — asegúrate de usar exactamente los mismos nombres.

## Cómo cambiar el tamaño

La escala se puede editar directamente en el menú del juego, pero también puedes ajustar los valores `x` e `y` si lo necesitas en el archivo `doors_creator/integrations/cl_integrations.lua`:

```lua
-- ancho de la imagen
x = 0.03,

-- altura de la imagen
y = 0.04,
```
