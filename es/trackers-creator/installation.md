---
title: "Instalación"
description: "Instala Trackers Creator con ESX o QBCore en tu servidor de FiveM, incluyendo la configuración opcional de items predeterminados."
icon: "download"
---

La instalación del script es extremadamente sencilla.

## Requisitos

- **ESX** o **QBCore**

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
        El script configurará la base de datos **automáticamente**. En caso de que no lo haga, puedes ejecutar manualmente los archivos de la carpeta `trackers_creator/sql/`.
      </Step>
    </Steps>

    ### Añadir los items — Opcional

    Para añadir los items predefinidos, solo tienes que ejecutar el archivo `trackers_creator/sql/items_limit.sql` **o** `trackers_creator/sql/items_weight.sql`, según si tu servidor usa límite o peso.

    <Info>
      La última versión de ESX usa **peso**.
    </Info>

    <Danger>
      Si no funciona, asegúrate de usar la última versión oficial de ESX con las dependencias necesarias.
    </Danger>
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
        El script configurará la base de datos **automáticamente**. En caso de que no lo haga, puedes ejecutar manualmente los archivos de la carpeta `trackers_creator/sql/`.
      </Step>
    </Steps>

    ### Añadir los items — Opcional

    Para añadir los nuevos items, edita el archivo `qb-core/shared/items.lua` y añade el siguiente código al final de la tabla:

    ```lua
    ['tracker_sender'] = {['name'] = 'tracker_sender', ['label'] = 'Tracker sender', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['tracker_receiver'] = {['name'] = 'tracker_receiver', ['label'] = 'Tracker receiver', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['private_tracker'] = {['name'] = 'private_tracker', ['label'] = 'Private tracker', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil},
    ```
  </Tab>
</Tabs>

¡Ya está todo listo! Disfruta del script 😁

## Verificación

<Info>
  [TODO: INFORMATION NEEDED] Todavía no hay documentada una comprobación en el juego para verificar una instalación exitosa de Trackers Creator.
</Info>

## Paso opcional

Una vez que la base de datos esté configurada correctamente, puedes eliminar los archivos de la carpeta `trackers_creator/sql/`, para que el script no intente configurar la base de datos cada vez que se inicie.
