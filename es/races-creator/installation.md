---
title: "Instalación"
description: "Instala Races Creator en tu servidor de FiveM."
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
    El script configurará la base de datos **automáticamente**. Si no lo hace, puedes ejecutar manualmente los archivos de la carpeta `races_creator/sql/`.
  </Step>
</Steps>

¡Ya está todo listo! Disfruta del script 😁

## Verificación

<Info>
  [TODO: INFORMATION NEEDED] Todavía no hay documentada una comprobación dentro del juego para verificar una instalación exitosa de Races Creator.
</Info>

<Note>
  Una vez que la base de datos se haya configurado correctamente, puedes eliminar opcionalmente los archivos SQL de `races_creator/sql/`, para que el script no intente configurarla de nuevo cada vez que se inicie.
</Note>
