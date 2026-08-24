---
title: "Instalación"
description: "Instala Vehicles Keys en tu servidor de FiveM con ESX o QBCore, incluyendo la configuración opcional de items predeterminados."
icon: "download"
---

La instalación del script es extremadamente sencilla.

## Requisitos

- **ESX** o **QBCore**
- El [script de lockpicking](https://github.com/baguscodestudio/lockpick) de [baguscodestudio](https://github.com/baguscodestudio/lockpick)
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
        El script configurará la base de datos **automáticamente**. En caso de que no lo haga, puedes ejecutar manualmente los archivos de la carpeta `vehicles_keys/sql/`.
      </Step>
      <Step title="Script de lockpicking">
        Descarga e inicia el [script de lockpicking](https://github.com/baguscodestudio/lockpick) _(créditos a [baguscodestudio](https://github.com/baguscodestudio/lockpick))_.
      </Step>
    </Steps>

    ### Añadir los items — Opcional

    Para añadir los items ya preparados, solo tienes que ejecutar el archivo `vehicles_keys/sql/items_limit.sql` **o** `vehicles_keys/sql/items_weight.sql`, dependiendo de si tu servidor usa limit o weight.

    <Info>
      La última versión de ESX usa **weight**.
    </Info>

    <Danger>
      Si no funciona, asegúrate de usar la última versión oficial de ESX con las dependencias requeridas.
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
        El script configurará la base de datos **automáticamente**. En caso de que no lo haga, puedes ejecutar manualmente los archivos de la carpeta `vehicles_keys/sql/`.
      </Step>
      <Step title="Script de lockpicking">
        Descarga e inicia el [script de lockpicking](https://github.com/baguscodestudio/lockpick) _(créditos a [baguscodestudio](https://github.com/baguscodestudio/lockpick))_.
      </Step>
      <Step title="Instalar menu_default">
        Descarga y extrae el script [menu_default](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing) en tus resources, **sin renombrarlo**, y añádelo a tu inicio automático (ejemplo: `server.cfg`).
      </Step>
    </Steps>

    ### Añadir los items — Opcional

    Para añadir los items nuevos, edita el archivo `qb-core/shared/items.lua` y añade el siguiente código al final de la tabla:

    ```lua
    -- Items de Vehicles Keys
    ['vehicle_alarm_1'] = {['name'] = 'vehicle_alarm_1', ['label'] = 'Vehicle alarm level 1', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Vehicle alarm level 1'},
    ['vehicle_alarm_2'] = {['name'] = 'vehicle_alarm_2', ['label'] = 'Vehicle alarm level 2', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Vehicle alarm level 2'},
    ['vehicle_alarm_3'] = {['name'] = 'vehicle_alarm_3', ['label'] = 'Vehicle alarm level 3', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Vehicle alarm level 3'},
    ['vehicle_alarm_4'] = {['name'] = 'vehicle_alarm_4', ['label'] = 'Vehicle alarm level 4', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Vehicle alarm level 4'},
    ['vehicle_transfer_contract'] = {['name'] = 'vehicle_transfer_contract', ['label'] = 'Vehicle transfer contract', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Used to sell your vehicle to someone'},
    ```

    <Frame caption="Captura de ejemplo">
      ![QBCore Vehicles Keys items example](/images/qb_core_vehicles_keys_items.png)
    </Frame>
  </Tab>
</Tabs>

¡Ya está todo listo! Disfruta del script 😁

## Verificación

<Info>
  [TODO: INFORMATION NEEDED] Todavía no hay documentada ninguna comprobación en el juego para verificar una instalación exitosa de Vehicles Keys.
</Info>

## Paso opcional

Una vez que la base de datos esté configurada correctamente, puedes eliminar los archivos de la carpeta `vehicles_keys/sql/`, para que el script no intente configurar la base de datos cada vez que se inicie.
