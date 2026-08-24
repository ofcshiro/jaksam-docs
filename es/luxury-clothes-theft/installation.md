---
title: "Instalación"
description: "Instala Luxury Clothes Theft con ESX o QBCore en tu servidor de FiveM, incluyendo la configuración opcional de items predeterminados."
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

<Tabs>
  <Tab title="ESX">
    <Steps>
      <Step title="Descargar y extraer">
        Descarga el script y extráelo en tus resources.
      </Step>
      <Step title="Añadir al inicio automático">
        Añade el script a tu inicio automático (ejemplo: `server.cfg`).
      </Step>
      <Step title="Configurar las opciones">
        Configura las opciones en los archivos de config (asegúrate de leer los comentarios, explican todo).
      </Step>
    </Steps>

    ### Añadir items — Opcional

    Para añadir los items predefinidos, solo tienes que ejecutar el archivo `luxury_clothes_theft/sql/items_limit.sql` **o** `luxury_clothes_theft/sql/items_weight.sql`, según si tu servidor usa límite o peso.

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
      <Step title="Configurar las opciones">
        Configura las opciones en los archivos de config (asegúrate de leer los comentarios, explican todo).
      </Step>
      <Step title="Instalar menu_default">
        Descarga y extrae el script [menu_default](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing) en tus resources, **sin renombrarlo**, y añádelo a tu inicio automático (ejemplo: `server.cfg`).
      </Step>
    </Steps>

    ### Añadir items

    Para añadir los nuevos items, edita el archivo `qb-core/shared/items.lua` y añade el siguiente código al final de la tabla:

    ```lua
    ['luxury_stolen_bag'] = {['name'] = 'luxury_stolen_bag', ['label'] = 'Luxury clothes bag', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['gucci_tshirt'] = {['name'] = 'gucci_tshirt', ['label'] = 'Gucci T-Shirt', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['gucci_flipflops'] = {['name'] = 'gucci_flipflops', ['label'] = 'Gucci Flip Flops', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['louis_vuitton_bag'] = {['name'] = 'louis_vuitton_bag', ['label'] = 'Louis Vuitton Bag', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['louis_vuitton_tshirt'] = {['name'] = 'louis_vuitton_tshirt', ['label'] = 'Louis Vuitton T-Shirt', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['valentino_pants'] = {['name'] = 'valentino_pants', ['label'] = 'Valentino Pants', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['prada_shoes'] = {['name'] = 'prada_shoes', ['label'] = 'Prada Shoes', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['prada_bag'] = {['name'] = 'prada_bag', ['label'] = 'Prada Bag', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ```

    <Frame caption="Captura de ejemplo">
      ![QBCore Luxury Clothes Theft items example](/images/qb_core_luxury_clothest_theft_items.jpg)
    </Frame>
  </Tab>
</Tabs>

¡Ya está todo listo! Disfruta del script 😁

## Verificación

<Info>
  [TODO: INFORMATION NEEDED] Todavía no hay documentada una comprobación en el juego para verificar una instalación exitosa de Luxury Clothes Theft.
</Info>
