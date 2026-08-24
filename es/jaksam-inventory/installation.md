---
title: "Instalación"
icon: "table-rows-add-below"
description: "La instalación del script es extremadamente sencilla."
---

## Requisitos

- **ESX** (1.10.7, 1.11.3\+, o 1.14.0\+), **QBCore**, o **QBX**
- `jaksam_core`
- `oxmysql` y `ox_lib` (consulta el ejemplo de orden de inicio para tu framework más abajo)

<Warning>
  **NO uses FileZilla** para subir los archivos, de lo contrario el script **NO** funcionará. Usa [WinSCP](https://winscp.net/eng/download.php) en su lugar.
</Warning>

<Tabs>
  <Tab title="ESX 1.10.7">
    1. Descarga el script y extráelo en tus resources.
    2. Descarga `jaksam_core` y extráelo en tus resources.
    3. Agrega el siguiente código **justo después** de `es_extended` en tu `server.cfg`:

    ```cfg
    add_unsafe_worker_permission jaksam_inventory # Permite que el inventario de jaksam se instale automáticamente
    ensure jaksam_inventory
    ```

    4. En `es_extended/config.lua`, configura:

    ```lua
    Config.OxInventory = false
    ```

    5. En `es_extended/config.lua`, configura:

    ```lua
    Config.EnableDefaultInventory = false
    ```

    6. El script configurará **automáticamente** la base de datos. Si no lo hace, puedes ejecutar manualmente los archivos de la carpeta `jaksam_inventory/sql/`.

    ### Ejemplo de Orden de Inicio

    ```cfg
    # OX
    ensure oxmysql
    ensure ox_lib
    
    ## ESX
    ensure es_extended
    ensure jaksam_inventory
    
    # Otros scripts de ESX
    start [core]
    ```

    <Warning>
      Si no funciona, asegúrate de usar la última versión del ESX oficial con todas las dependencias necesarias.
    </Warning>
  </Tab>
  <Tab title="ESX 1.11.3+">
    1. Descarga el script y extráelo en tus resources.
    2. Descarga `jaksam_core` y extráelo en tus resources.
    3. Agrega el siguiente código **justo después** de `es_extended` en tu `server.cfg`:

    ```cfg
    add_unsafe_worker_permission jaksam_inventory # Permite que el inventario de jaksam se instale automáticamente
    ensure jaksam_inventory
    ```

    4. En `es_extended/config.lua`, configura:

    ```lua
    Config.CustomInventory = "jaksam_inventory"
    ```

    5. El script configurará **automáticamente** la base de datos. Si no lo hace, puedes ejecutar manualmente los archivos de la carpeta `jaksam_inventory/sql/`.

    ### Ejemplo de Orden de Inicio

    ```cfg
    # OX
    ensure oxmysql
    ensure ox_lib
    
    ## ESX
    ensure es_extended
    ensure jaksam_inventory
    
    # Otros scripts de ESX
    start [core]
    ```
  </Tab>
  <Tab title="ESX 1.14.0+">
    1. Descarga el script y extráelo en tus resources.
    2. Descarga `jaksam_core` y extráelo en tus resources.
    3. Agrega el siguiente código **justo después** de `es_extended` en tu `server.cfg`:

    ```cfg
    add_unsafe_worker_permission jaksam_inventory # Permite que el inventario de jaksam se instale automáticamente
    ensure jaksam_inventory
    ```

    4. En `es_extended/shared/config/main.lua`, configura:

    ```lua
    Config.CustomInventory = "jaksam_inventory"
    ```

    5. El script configurará **automáticamente** la base de datos. Si no lo hace, puedes ejecutar manualmente los archivos de la carpeta `jaksam_inventory/sql/`.

    ### Ejemplo de Orden de Inicio

    ```cfg
    # OX
    ensure oxmysql
    ensure ox_lib
    
    ## ESX
    ensure es_extended
    ensure jaksam_inventory
    
    # Otros scripts de ESX
    start [core] ## Cambia "ensure" por "start" para que no reinicie es_extended
    ```
  </Tab>
  <Tab title="QBCore">
    1. Descarga el script y extráelo en tus resources.
    2. Descarga `jaksam_core` y extráelo en tus resources.
    3. Habilita `Integrations.backwardsCompatibility` para `qb-inventory` en `jaksam_inventory/integrations/sv_integrations.lua`.
    4. Agrega el siguiente código **justo después** de `qb-core` en tu `server.cfg`:

    ```cfg
    add_unsafe_worker_permission jaksam_inventory # Permite que el inventario de jaksam se instale automáticamente
    ensure jaksam_inventory
    ```

    5. El script configurará **automáticamente** la base de datos. Si no lo hace, puedes ejecutar manualmente los archivos de la carpeta `jaksam_inventory/sql/`.

    ### Ejemplo de Orden de Inicio

    ```cfg
    # OX
    ensure oxmysql
    ensure ox_lib
    
    ## QBCore
    ensure qb-core
    ensure jaksam_inventory
    
    # Otros scripts de QBCore
    start [qb] ## Si decía "ensure", cámbialo a "start" para que no reinicie qb-core
    ```

    <Warning>
      Si no funciona, asegúrate de usar la última versión del QBCore oficial con todas las dependencias necesarias.
    </Warning>
  </Tab>
  <Tab title="QBX">
    1. Descarga el script y extráelo en tus resources.
    2. Descarga `jaksam_core` y extráelo en tus resources.
    3. Habilita `Integrations.backwardsCompatibility` para `ox_inventory` en `jaksam_inventory/integrations/sv_integrations.lua`.
    4. Agrega el siguiente código **justo después** de `qbx_core` en tu `server.cfg`:

    ```cfg
    add_unsafe_worker_permission jaksam_inventory # Permite que el inventario de jaksam se instale automáticamente
    ensure jaksam_inventory
    ```

    5. El script configurará **automáticamente** la base de datos. Si no lo hace, puedes ejecutar manualmente los archivos de la carpeta `jaksam_inventory/sql/`.

    ### Ejemplo de Orden de Inicio

    ```cfg
    # OX
    ensure oxmysql
    ensure ox_lib
    
    ## QBX
    ensure qbx_core
    ensure jaksam_inventory
    
    # Otros scripts de QBX
    ```

    <Warning>
      Si no funciona, asegúrate de usar la última versión del QBX oficial con todas las dependencias necesarias.
    </Warning>
  </Tab>
</Tabs>

¡Ya está todo listo! Disfruta del script 😁

## Verificación

Usa el comando `/inventory` dentro del juego. Si tu inventario se abre, el script está funcionando correctamente.

## Importar Ítems e Inventarios Antiguos

<Tabs>
  <Tab title="ESX">
    1. Entra al juego.
    2. Usa el comando `/inventory` y ve a **Settings**.
    3. Haz clic en **Import from ESX**.
    4. ¡Listo!
  </Tab>
  <Tab title="QBCore">
    1. Solo durante este proceso, asegúrate de que el **`qb-inventory` original** esté activo. Después de la importación, puedes y debes eliminarlo.
    2. Usa el comando `/inventory` y ve a **Settings**.
    3. Haz clic en **Import from QBCore**.
    4. ¡Listo!
  </Tab>
  <Tab title="OX Inventory">
    1. Solo durante este proceso, asegúrate de que `ox_inventory` esté activo. Después de la importación, puedes y debes eliminarlo.
    2. Usa el comando `/inventory` y ve a **Settings**.
    3. Haz clic en **Import from OX inventory**.
    4. ¡Listo!
  </Tab>
  <Tab title="qs-inventory">
    1. Solo durante este proceso, asegúrate de que `qs-inventory` esté activo. Después de la importación, puedes y debes eliminarlo.
    2. Usa el comando `/inventory` y ve a **Settings**.
    3. Haz clic en **Import from qs-inventory**.
    4. ¡Listo!
  </Tab>
  <Tab title="Chezza Inventory">
    1. Solo durante este proceso, asegúrate de que el **inventario Chezza** esté activo. Después de la importación, puedes y debes eliminarlo.
    2. Usa el comando `/inventory` y ve a **Settings**.
    3. Haz clic en **Import from Chezza inventory**.
    4. ¡Listo!
  </Tab>
  <Tab title="TGiann Inventory">
    1. Solo durante este proceso, asegúrate de que el **inventario TGiann** esté activo. Después de la importación, puedes y debes eliminarlo.
    2. Usa el comando `/inventory` y ve a **Settings**.
    3. Haz clic en **Import from TGiann inventory**.
    4. ¡Listo!
  </Tab>
</Tabs>

## Compatibilidad con Versiones Anteriores

Este inventario te permite seguir usando tus scripts antiguos, incluso si requieren un sistema de inventario diferente.

### Funciones Predeterminadas del Framework

Puedes usar las funciones de inventario normales que ofrece tu framework.

### Compatibilidad con OX Inventory

Si tus scripts antiguos usan **OX Inventory**, puedes habilitar una compatibilidad sencilla.

1. Ve a `jaksam_inventory/integrations/sv_integrations.lua`.
2. Habilita `ox_inventory` en `Integrations.backwardsCompatibility`.
3. Es posible que el servidor necesite reiniciarse después de cargar por primera vez con esta configuración.

### Compatibilidad con QB Inventory

Si tus scripts antiguos usan **QB Inventory**, puedes habilitar una compatibilidad sencilla.

1. Ve a `jaksam_inventory/integrations/sv_integrations.lua`.
2. Habilita `qb-inventory` en `Integrations.backwardsCompatibility`.
3. Es posible que el servidor necesite reiniciarse después de cargar por primera vez con esta configuración.

¡Eso es todo! Tus scripts antiguos ahora deberían funcionar con este inventario.
