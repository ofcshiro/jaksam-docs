---
title: "Cómo añadir audio e imágenes personalizados a los efectos"
description: "Añade tu propia música o imágenes a los efectos de las drogas colocando archivos en la carpeta correcta."
icon: "photo-film"
---

<Tip>
  ¿Quieres añadir tu propia música o imágenes a los efectos de las drogas? Solo tienes que colocar los archivos en la carpeta correcta.
</Tip>

El script escanea automáticamente las carpetas de assets y muestra todos los archivos válidos en el desplegable del editor de efectos. No hace falta cambiar nada de código.

## Añadir archivos de audio personalizados

<Steps>
  <Step title="Ve a la carpeta de audio">
    Abre los archivos de tu servidor y ve a `drugs_creator/html/assets/audio/`.
  </Step>
  <Step title="Añade tus archivos">
    Coloca tus archivos de audio en esta carpeta.
  </Step>
  <Step title="Reinicia">
    Reinicia el script o el servidor.
  </Step>
</Steps>

¡Eso es todo! Los nuevos archivos de audio aparecerán ahora en el desplegable del efecto **Music** al editar los efectos de las drogas.

### Formatos de audio soportados

`mp3`, `ogg`, `wav`, `flac`, `aac`, `m4a`

## Añadir imágenes personalizadas

<Steps>
  <Step title="Ve a la carpeta de imágenes">
    Abre los archivos de tu servidor y ve a `drugs_creator/html/assets/img/`.
  </Step>
  <Step title="Añade tus archivos">
    Coloca tus archivos de imagen en esta carpeta.
  </Step>
  <Step title="Reinicia">
    Reinicia el script o el servidor.
  </Step>
</Steps>

Las nuevas imágenes aparecerán en los desplegables de los efectos **Trip Screen Image** y **3D World Image**.

### Formatos de imagen soportados

`jpg`, `jpeg`, `png`, `gif`, `webp`

## Notas importantes

- Los nombres de archivo se usan directamente como etiquetas en el desplegable, así que usa nombres descriptivos (por ejemplo `space_trip.jpg` en lugar de `img1.jpg`)
- Si añades archivos mientras el servidor está en marcha, reinicia el script para que aparezcan los cambios
- Mantén un tamaño de archivo razonable — las imágenes o archivos de audio grandes pueden afectar los tiempos de carga de los jugadores
