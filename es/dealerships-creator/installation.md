---
title: "Instalación"
description: "Instala Dealerships Creator en tu servidor de FiveM, incluyendo la generación automática opcional de imágenes de vehículos."
icon: "download"
---

La instalación del script es extremadamente fácil.

<Danger>
  **NO** uses FileZilla para subir los archivos, de lo contrario el script **NO** funcionará.

  Usa [WinSCP](https://winscp.net/eng/download.php) en su lugar.
</Danger>

<Steps>
  <Step title="Descarga y extrae">
    Descarga el script y extráelo en tus resources.
  </Step>
  <Step title="Añade al auto start">
    Añade el script en tu auto start (ejemplo: `server.cfg`).
  </Step>
  <Step title="Configuración de la base de datos">
    El script configurará la base de datos **automáticamente**. En caso de que no lo haga, puedes ejecutar manualmente los archivos de la carpeta `dealerships_creator/sql/`.
  </Step>
</Steps>

¡Ya estás listo! Disfruta del script 😁

## Verificación

<Info>
  [TODO: INFORMACIÓN NECESARIA] Todavía no hay documentada una comprobación in-game para verificar una instalación exitosa de Dealerships Creator.
</Info>

<Note>
  Una vez que la base de datos se haya configurado correctamente, puedes eliminar opcionalmente los archivos SQL de `dealerships_creator/sql/`, para que el script no intente configurarla de nuevo cada vez que arranca.
</Note>

## Creación automática de imágenes — Opcional

Si quieres usar la creación automática de imágenes de vehículos, sigue estos pasos:

<Steps>
  <Step title="Instala screenshot-basic">
    Instala [screenshot-basic](https://github.com/citizenfx/screenshot-basic) (probablemente ya lo tengas).
  </Step>
  <Step title="Instala yarn">
    Instala [yarn](https://github.com/citizenfx/cfx-server-data) (probablemente ya lo tengas — `resources/[system]/[builders]`).
  </Step>
  <Step title="Instala webpack">
    Instala [webpack](https://github.com/citizenfx/cfx-server-data) (probablemente ya lo tengas — `resources/[system]/[builders]`).
  </Step>
  <Step title="Configura los permisos de la carpeta">
    Asegúrate de que la carpeta `dealerships_creator` y la carpeta `dealerships_creator/_vehicles_images` tengan permisos de lectura/escritura (clic derecho en las carpetas → Propiedades → activa los permisos de lectura (**R**) y escritura (**W**)).
  </Step>
</Steps>
