---
title: "Instalación"
description: "Instala Easy Allowlist & Queue en tu servidor de FiveM."
icon: "download"
---

La instalación del script es extremadamente sencilla.

<Danger>
  **NO** uses FileZilla para subir los archivos, de lo contrario el script **NO** funcionará.

  Usa [WinSCP](https://winscp.net/eng/download.php) en su lugar.
</Danger>

<Steps>
  <Step title="Descarga y extrae">
    Descarga el script y extráelo en tus resources.
  </Step>
  <Step title="Añádelo al auto start">
    Añade el script a tu auto start (ejemplo: `server.cfg`).
  </Step>
  <Step title="Configuración de la base de datos">
    El script configurará la base de datos **automáticamente**. Si no lo hace, puedes ejecutar manualmente los archivos de la carpeta `easy_allowlist/sql/`.
  </Step>
  <Step title="Date whitelist a ti mismo">
    Para añadirte a la allowlist, usa el comando `add_allowlist REQUEST_ID` en la consola del servidor después de haber enviado la solicitud.
  </Step>
  <Step title="Configura los ajustes ingame">
    Configura los ajustes ingame siguiendo también esta guía.
  </Step>
</Steps>

¡Ya está todo listo! Disfruta del script 😁

## Verificación

Ejecuta `add_allowlist REQUEST_ID` en la consola del servidor (según el paso "Date whitelist a ti mismo" anterior). Si el comando se reconoce y se ejecuta sin un error de comando desconocido, el script está funcionando correctamente.

<Note>
  Una vez configurada correctamente la base de datos, puedes eliminar opcionalmente los archivos SQL de `easy_allowlist/sql/`, para que el script no intente configurarla de nuevo cada vez que se inicie.
</Note>
