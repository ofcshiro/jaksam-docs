---
title: "Personalizar el Tema Predeterminado"
description: "Configura un tema predeterminado personalizado para todos los jugadores de tu servidor, paso a paso"
icon: "palette"
---

¿Quieres que todos los jugadores tengan el mismo tema predeterminado? Así se hace, paso a paso.

<Steps>
  <Step title="Abre tu inventario">
    Presiona **F2** dentro del juego para abrir tu inventario.
  </Step>
  <Step title="Abre el editor de temas">
    Haz clic en el botón **Theme** (esquina inferior derecha).

    <Frame>
      ![Personalización del tema del inventario 1](/images/inventory-theme-1.jpg)
    </Frame>
  </Step>
  <Step title="Personaliza y guarda">
    Cambia los colores y estilos como quieras, luego presiona **Save**.
  </Step>
  <Step title="Selecciona tu tema">
    Asegúrate de que tu tema personalizado esté seleccionado.

    <Frame>
      ![Personalización del tema del inventario 2](/images/inventory-theme-2.jpg)
    </Frame>
  </Step>
  <Step title="Abre la consola">
    Presiona **F8** para abrir la consola, luego escribe:

    ```bash
        admintheme
    ```
  </Step>
  <Step title="Copia el código del tema">
    Verás un montón de código.

    <Note>
      Copia _todo_ lo que está entre `COPY FROM THE LINE BELOW` y `COPY TILL THE LINE ABOVE` — no te olvides de los bordes.
    </Note>

    <Frame>
      ![Personalización del tema del inventario 3](/images/inventory-theme-3.jpg)
    </Frame>
  </Step>
  <Step title="Abre el archivo del tema">
    Ve a los archivos del servidor y abre:

    ```text
        jaksam_inventory/dist/assets/variables.css
    ```
  </Step>
  <Step title="Pega y reemplaza">
    Pega lo que copiaste, reemplazando **todo** el contenido de ese archivo.
  </Step>
  <Step title="Reinicia">
    Reinicia el script o recarga el servidor.
  </Step>
</Steps>

<Tip>
  ¡Eso es todo! Ahora el tema predeterminado de todos usará tus colores y ajustes personalizados (a menos que ellos mismos lo cambien).
</Tip>
