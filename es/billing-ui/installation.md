---
title: "Instalación"
description: "Instala Billing UI en tu servidor de FiveM con ESX o QBCore."
icon: "download"
---

La instalación del script es extremadamente sencilla.

## Requisitos

- **ESX** o **QBCore**
- En ESX, `esx_billing` debe eliminarse (consulta la advertencia a continuación)
- En QBCore, el script [`menu_default`](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing)

<Danger>
  **NO** uses FileZilla para subir los archivos, de lo contrario el script **NO** funcionará.

  Usa [WinSCP](https://winscp.net/eng/download.php) en su lugar.
</Danger>

<Tabs>
  <Tab title="ESX">
    <Steps>
      <Step title="Descargar y extraer">
        Descarga el script y extráelo en tus resources.
      </Step>
      <Step title="Añadir al inicio automático">
        Añade el script a tu inicio automático (ejemplo: `server.cfg`).
      </Step>
      <Step title="Configuración de la base de datos">
        El script configurará la base de datos **automáticamente**. Si no lo hace, puedes ejecutar manualmente los archivos de la carpeta `billing_ui/sql/`.
      </Step>
      <Step title="Configurar las opciones">
        Configura las opciones en los archivos de configuración (asegúrate de leer los comentarios, explican todo).
      </Step>
    </Steps>

    <Warning>
      Asegúrate de eliminar `esx_billing` para evitar problemas.
    </Warning>
  </Tab>
  <Tab title="QBCore">
    <Steps>
      <Step title="Descargar y extraer">
        Descarga el script y extráelo en tus resources.
      </Step>
      <Step title="Añadir al inicio automático">
        Añade el script a tu inicio automático (ejemplo: `server.cfg`).
      </Step>
      <Step title="Configuración de la base de datos">
        El script configurará la base de datos **automáticamente**. Si no lo hace, puedes ejecutar manualmente los archivos de la carpeta `billing_ui/sql/`.
      </Step>
      <Step title="Configurar las opciones">
        Configura las opciones en los archivos de configuración (asegúrate de leer los comentarios, explican todo).
      </Step>
      <Step title="Instalar menu_default">
        Descarga y extrae el script [menu_default](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing) en tus resources, **sin renombrarlo**, y añádelo a tu inicio automático (ejemplo: `server.cfg`).
      </Step>
    </Steps>
  </Tab>
</Tabs>

¡Ya está todo listo! Disfruta del script 😁

## Verificación

<Info>
  [TODO: INFORMATION NEEDED] Todavía no hay documentada una comprobación dentro del juego para verificar una instalación exitosa de Billing UI.
</Info>

## Paso opcional

Una vez que la base de datos esté configurada correctamente, puedes eliminar los archivos de la carpeta `billing_ui/sql/`, para que el script no intente configurar la base de datos cada vez que lo inicies.
