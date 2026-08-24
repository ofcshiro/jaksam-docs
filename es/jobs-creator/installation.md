---
title: "Instalación"
description: "Instala Jobs Creator en tu servidor de FiveM con ESX o QBCore. Sigue la guía de configuración específica del framework y configura la base de datos y los items necesarios."
icon: "download"
---

Pon en marcha **Jobs Creator** en tu servidor de FiveM en solo unos pasos.

## Requisitos

- **ESX** o **QBCore**
- En QBCore, el script [`menu_default`](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing) (ver el paso 4 más abajo)

Elige tu framework a continuación para ver las instrucciones de instalación correctas.

<Tabs>
  <Tab title="ESX" icon="server">
    <Steps>
      <Step title="Descarga Jobs Creator">
        Descarga **Jobs Creator** y extráelo en la carpeta `resources` de tu servidor.
      </Step>
      <Step title="Configura server.cfg">
        Añade lo siguiente a tu `server.cfg`:

        ```cfg
        add_unsafe_worker_permission jobs_creator # Permite que jobs_creator se instale automáticamente
        ensure jobs_creator
        ```
      </Step>
      <Step title="Configura la base de datos">
        Jobs Creator **configurará automáticamente la base de datos** al iniciar el resource.

        Si la configuración automática falla, puedes ejecutar manualmente los archivos SQL ubicados en:

        ```text
        jobs_creator/sql/
        ```
      </Step>
      <Step title="Añade los items incluidos">
        <Note>
          Añadir los items incluidos es **opcional**. Elige el archivo SQL que coincida con tu sistema de inventario de ESX.
        </Note>

        **Inventario basado en peso**

        Ejecuta:

        ```text
        jobs_creator/sql/items_weight.sql
        ```

        **Inventario basado en límite**

        Ejecuta:

        ```text
        jobs_creator/sql/items_limit.sql
        ```
      </Step>
    </Steps>
  </Tab>
  <Tab title="QBCore" icon="server">
    <Steps>
      <Step title="Descarga Jobs Creator">
        Descarga **Jobs Creator** y extráelo en la carpeta `resources` de tu servidor.
      </Step>
      <Step title="Configura server.cfg">
        Añade lo siguiente a tu `server.cfg`:

        ```cfg
        add_unsafe_worker_permission jobs_creator # Permite que jobs_creator se instale automáticamente
        ensure jobs_creator
        ```
      </Step>
      <Step title="Configura la base de datos">
        Jobs Creator **configurará automáticamente la base de datos** al iniciar el resource.

        Si la configuración automática falla, puedes ejecutar manualmente los archivos SQL ubicados en:

        ```text
        jobs_creator/sql/
        ```
      </Step>
      <Step title="Instala menu_default">
        Descarga [`menu_default`](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing) y extráelo en la carpeta `resources` de tu servidor.

        Luego añade `menu_default` a tu `server.cfg`:

        ```cfg
        ensure menu_default
        ```
      </Step>
      <Step title="Añade los items incluidos">
        <Note>
          Añadir los items incluidos es **opcional**.
        </Note>

        Abre:

        ```text
        qb-core/shared/items.lua
        ```

        Añade los siguientes items al final de la tabla de items:

        ```lua
        ['fixkit'] = {
            ['name'] = 'fixkit',
            ['label'] = 'Fixkit',
            ['weight'] = 500,
            ['type'] = 'item',
            ['image'] = 'your_image.png',
            ['unique'] = false,
            ['useable'] = false,
            ['shouldClose'] = false,
            ['combinable'] = nil
        },
        
        ['medikit'] = {
            ['name'] = 'medikit',
            ['label'] = 'Medikit',
            ['weight'] = 500,
            ['type'] = 'item',
            ['image'] = 'your_image.png',
            ['unique'] = false,
            ['useable'] = false,
            ['shouldClose'] = false,
            ['combinable'] = nil
        },
        
        ['sponge'] = {
            ['name'] = 'sponge',
            ['label'] = 'Sponge',
            ['weight'] = 500,
            ['type'] = 'item',
            ['image'] = 'your_image.png',
            ['unique'] = false,
            ['useable'] = false,
            ['shouldClose'] = false,
            ['combinable'] = nil
        },
        
        ['handcuffs'] = {
            ['name'] = 'handcuffs',
            ['label'] = 'Handcuffs',
            ['weight'] = 500,
            ['type'] = 'item',
            ['image'] = 'your_image.png',
            ['unique'] = false,
            ['useable'] = false,
            ['shouldClose'] = false,
            ['combinable'] = nil
        },
        
        ['lockpick'] = {
            ['name'] = 'lockpick',
            ['label'] = 'Lockpick',
            ['weight'] = 500,
            ['type'] = 'item',
            ['image'] = 'your_image.png',
            ['unique'] = false,
            ['useable'] = false,
            ['shouldClose'] = false,
            ['combinable'] = nil
        },
        
        ['bandage'] = {
            ['name'] = 'bandage',
            ['label'] = 'Bandage',
            ['weight'] = 500,
            ['type'] = 'item',
            ['image'] = 'your_image.png',
            ['unique'] = false,
            ['useable'] = false,
            ['shouldClose'] = false,
            ['combinable'] = nil
        },
        ```
      </Step>
    </Steps>
  </Tab>
</Tabs>

## Verificación

Abre `/jobscreator` dentro del juego. Si el menú se abre, el script está funcionando correctamente.

## Limpiar los Archivos SQL

<Note>
  Una vez que la base de datos se haya configurado correctamente, puedes eliminar opcionalmente los archivos SQL de `jobs_creator/sql/`.
</Note>

Los archivos SQL solo son necesarios para la configuración manual de la base de datos o al añadir los items incluidos de ESX.
