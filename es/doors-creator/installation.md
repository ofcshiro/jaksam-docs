---
title: "Instalación"
description: "Instala Doors Creator en tu servidor de FiveM."
icon: "download"
---

La instalación del script es extremadamente sencilla.

## Requisitos

- El [script de lockpicking](https://github.com/baguscodestudio/lockpick) de [baguscodestudio](https://github.com/baguscodestudio/lockpick)
- Un item `doors_lockpick` añadido a tu sistema de inventario

<Danger>
  **NO** uses FileZilla para subir los archivos, de lo contrario el script **NO** funcionará.

  Usa [WinSCP](https://winscp.net/eng/download.php) en su lugar.
</Danger>

<Steps>
  <Step title="Descargar y extraer">
    Descarga el script y extráelo en tus resources.
  </Step>
  <Step title="Añadir al inicio automático">
    Añade el script a tu inicio automático (ejemplo: `server.cfg`).
  </Step>
  <Step title="Configuración de la base de datos">
    El script configurará la base de datos **automáticamente**. En caso de que no lo haga, puedes ejecutar manualmente los archivos de la carpeta `doors_creator/sql/`.
  </Step>
  <Step title="Script de lockpicking">
    Descarga e inicia el [script de lockpicking](https://github.com/baguscodestudio/lockpick) _(créditos a [baguscodestudio](https://github.com/baguscodestudio/lockpick))_.
  </Step>
  <Step title="Añadir el item de ganzúa">
    Añade el item `doors_lockpick` a tu lista de items, como harías con cualquier script.
  </Step>
  <Step title="Configurar el script">
    Configura el script desde el menú de administrador en el juego `/doorscreator`.
  </Step>
</Steps>

¡Ya está todo listo! Disfruta del script 😁

## Verificación

Abre `/doorscreator` en el juego. Si se abre el menú de administrador, el script está funcionando correctamente.

<Note>
  Una vez que la base de datos se haya configurado correctamente, puedes eliminar opcionalmente los archivos SQL de `doors_creator/sql/`, para que el script no intente configurarla de nuevo cada vez que se inicie.
</Note>
