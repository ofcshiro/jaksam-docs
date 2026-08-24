---
title: "Instalación"
description: "Instala Shops Creator en tu servidor de FiveM."
icon: "download"
---

La instalación del script es extremadamente fácil.

## Requisitos

- El [script de caja fuerte](https://github.com/VHall1/pd-safe) de [VHall1](https://github.com/VHall1) (si quieres la función de romper cajas fuertes)

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
    El script configurará la base de datos **automáticamente**. En caso de que no lo haga, puedes ejecutar manualmente los archivos de la carpeta `shops_creator/sql/`.
  </Step>
  <Step title="Script de caja fuerte">
    Descarga e inicia el [script de caja fuerte](https://github.com/VHall1/pd-safe) _(créditos a [VHall1](https://github.com/VHall1))_.
  </Step>
</Steps>

¡Ya estás listo! Disfruta del script 😁

## Verificación

Abre `/shopscreator` in-game. Si el menú se abre, el script está funcionando correctamente.

<Note>
  Una vez que la base de datos se haya configurado correctamente, puedes eliminar opcionalmente los archivos SQL de `shops_creator/sql/`, para que el script no intente configurarla de nuevo cada vez que arranca.
</Note>
