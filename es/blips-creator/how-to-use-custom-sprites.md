---
title: "Cómo usar sprites personalizados"
description: "Reemplaza los sprites de blips predeterminados por tus propios íconos personalizados."
icon: "image"
---

Blips Creator ofrece una forma extremadamente sencilla de reemplazar los sprites de los blips.

<Steps>
  <Step title="Elige un ícono">
    Elige un ícono `.png` que quieras usar (64x64px es lo mejor).
  </Step>
  <Step title="Abre la carpeta de sprites">
    Ve a la carpeta `blips_creator/_sprites/REPLACEABLE`.
  </Step>
  <Step title="Marca el sprite a reemplazar">
    Elige un sprite para reemplazar, copia su nombre y añade un `#` antes del nombre (para que sea más fácil de encontrar más adelante si lo necesitas).
  </Step>
  <Step title="Añade tu ícono">
    Coloca el nuevo ícono con el mismo nombre que el sprite anterior.
  </Step>
  <Step title="Reinicia el script">
    Reinicia Blips Creator **2 veces**.
  </Step>
</Steps>

## Ejemplo con imágenes

En este ejemplo, el logo verde se reemplaza por el sprite rojo.

<Frame caption="Carpeta blips_creator/_sprites/REPLACEABLE">
  ![REPLACEABLE folder](/images/immagine-1.png)
</Frame>

<Frame caption="Copia el nombre del archivo">
  ![Copy the file name](/images/immagine-8.png)
</Frame>

<Frame caption='Añade un "#" antes del nombre'>
  ![Add a hash before the name](/images/immagine-2.png)
</Frame>

<Frame caption="Renombra el archivo de tu nuevo ícono">
  ![Rename the new icon file](/images/immagine-4.png)
</Frame>

<Frame caption="Resultado final">
  ![Final result](/images/immagine-7.png)
</Frame>

Ahora reinicia el script **2 veces** y el sprite quedará actualizado.
