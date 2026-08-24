---
title: "Instalación"
description: "Instala Farming Creator con ESX o QBCore en tu servidor de FiveM."
icon: "download"
---

La instalación del script es extremadamente sencilla.

## Requisitos

- **ESX** o **QBCore**
- En QBCore, el script [`menu_default`](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing)

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
    El script configurará la base de datos **automáticamente**. En caso de que no lo haga, puedes ejecutar manualmente los archivos de la carpeta `farming_creator/sql/`.
  </Step>
  <Step title="Instalar menu_default (solo QBCore)">
    Descarga y extrae el script [menu_default](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing) en tus resources, **sin renombrarlo**, y añádelo a tu inicio automático (ejemplo: `server.cfg`).
  </Step>
</Steps>

¡Ya está todo listo! Disfruta del script 😁

## Verificación

<Info>
  [TODO: INFORMATION NEEDED] Todavía no hay documentada una comprobación en el juego para verificar una instalación exitosa de Farming Creator.
</Info>

<Note>
  Una vez que la base de datos se haya configurado correctamente, puedes eliminar opcionalmente los archivos SQL de `farming_creator/sql/`, para que el script no intente configurarla de nuevo cada vez que se inicie.
</Note>
