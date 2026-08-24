---
title: "Instalación"
description: "Instala Missions Creator en tu servidor de FiveM con ESX o QBCore, incluyendo scripts de minijuegos opcionales."
icon: "download"
---

La instalación del script es extremadamente sencilla.

## Requisitos

- **ESX** o **QBCore**
- `jaksam_core`, iniciado antes que `missions_creator`
- Scripts de minijuegos opcionales (consulta el último paso a continuación) si quieres usarlos

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
      <Step title="Descargar jaksam_core">
        Descarga `jaksam_core` y extráelo en tus resources.
      </Step>
      <Step title="Añadir jaksam_core al inicio automático">
        Añade `jaksam_core` a tu inicio automático (ejemplo: `server.cfg`).
      </Step>
      <Step title="Añadir missions_creator al inicio automático">
        Inicia `missions_creator` **después** de `jaksam_core`.
      </Step>
      <Step title="Configuración de la base de datos">
        El script configurará la base de datos **automáticamente**. Si no lo hace, puedes ejecutar manualmente los archivos de la carpeta `missions_creator/sql/`.
      </Step>
      <Step title="Scripts de minijuegos opcionales">
        - Descarga e inicia el [script de minijuego datacrack](https://github.com/utkuali/datacrack) _(créditos a [utkuali](https://github.com/utkuali))_
        - Descarga e inicia el [script de minijuego fingerprint](https://github.com/utkuali/Finger-Print-Hacking-Game) _(créditos a [utkuali](https://github.com/utkuali))_
        - Descarga e inicia el [script de minijuego memory](https://github.com/ultrahacx/ultra-keypackhack) _(créditos a [ultrahacx](https://github.com/ultrahacx))_
      </Step>
    </Steps>

    <Danger>
      Si no funciona, asegúrate de usar la última versión oficial de ESX con las dependencias requeridas.
    </Danger>
  </Tab>
  <Tab title="QBCore">
    <Steps>
      <Step title="Descargar y extraer">
        Descarga el script y extráelo en tus resources.
      </Step>
      <Step title="Descargar jaksam_core">
        Descarga `jaksam_core` y extráelo en tus resources.
      </Step>
      <Step title="Añadir jaksam_core al inicio automático">
        Añade `jaksam_core` a tu inicio automático (ejemplo: `server.cfg`).
      </Step>
      <Step title="Añadir missions_creator al inicio automático">
        Inicia `missions_creator` **después** de `jaksam_core`.
      </Step>
      <Step title="Configuración de la base de datos">
        El script configurará la base de datos **automáticamente**. Si no lo hace, puedes ejecutar manualmente los archivos de la carpeta `missions_creator/sql/`.
      </Step>
      <Step title="Scripts de minijuegos opcionales">
        - Descarga e inicia el [script de minijuego datacrack](https://github.com/utkuali/datacrack) _(créditos a [utkuali](https://github.com/utkuali))_
        - Descarga e inicia el [script de minijuego fingerprint](https://github.com/utkuali/Finger-Print-Hacking-Game) _(créditos a [utkuali](https://github.com/utkuali))_
        - Descarga e inicia el [script de minijuego memory](https://github.com/ultrahacx/ultra-keypackhack) _(créditos a [ultrahacx](https://github.com/ultrahacx))_
      </Step>
    </Steps>
  </Tab>
</Tabs>

¡Ya está todo listo! Disfruta del script 😁

## Verificación

<Info>
  [TODO: INFORMATION NEEDED] La documentación existente menciona un menú de administrador dentro del juego (las misiones referencian su ID "la que ves en el menú de administrador") pero no indica el comando para abrirlo. Añádelo aquí una vez confirmado.
</Info>

## Paso opcional

Una vez que la base de datos esté configurada correctamente, puedes eliminar los archivos de la carpeta `missions_creator/sql/`, para que el script no intente configurar la base de datos cada vez que lo inicies.
