---
title: "Instalación"
description: "Instala Blips Creator en tu servidor de FiveM."
icon: "download"
---

La instalación del script es extremadamente sencilla.

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
    El script configurará la base de datos **automáticamente**. En caso de que no lo haga, puedes ejecutar manualmente los archivos de la carpeta `blips_creator/sql/`.
  </Step>
  <Step title="Configurar las opciones">
    Configura las opciones en los archivos de config (asegúrate de leer los comentarios, explican todo).
  </Step>
  <Step title="Abrir el menú">
    Para abrir el menú, presiona `BARRA ESPACIADORA` mientras estás en el mapa grande del juego.
  </Step>
</Steps>

¡Ya está todo listo! Disfruta del script 😁

## Verificación

Presiona `BARRA ESPACIADORA` mientras estás en el mapa grande del juego. Si se abre el menú de blips, el script está funcionando correctamente.

<Note>
  Una vez que la base de datos se haya configurado correctamente, puedes eliminar opcionalmente los archivos SQL de `blips_creator/sql/`, para que el script no intente configurarla de nuevo cada vez que se inicie.
</Note>
