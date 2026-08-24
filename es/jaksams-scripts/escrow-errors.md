---
title: "Errores de Escrow"
description: "Soluciones para errores comunes causados por el sistema de escrow de assets de FiveM"
icon: "lock-hashtag"
---

<Danger>
  Si los scripts funcionan y dejan de funcionar tras reiniciar el servidor varias veces, tienes un virus en tu servidor. En ese caso no podemos ayudarte.
</Danger>

Aquí encontrarás las soluciones a errores comunes al usar los scripts de jaksam causados por el sistema de Escrow de FiveM.

Para verificar si tu error está causado por el escrow de assets de FiveM, simplemente reinicia el script y revisa **tanto** la **consola F8** como la **consola del servidor** (txAdmin) en busca de errores.

## ¿Cómo sé si mi error está causado por el sistema de escrow de FiveM?

Para entender si algo en un script no funciona por culpa del sistema de escrow de assets de FiveM, haz lo siguiente:

<Steps>
  <Step title="Reinicia el script">
    Reinicia el script que da problemas, usando el comando `ensure nombre_de_tu_script` en la consola de txAdmin o reiniciándolo como sueles hacerlo.

    <Frame caption="ejemplo de reinicio con F8 en el juego">
      ![in-game F8 restart example](/images/f8_restart.gif)
    </Frame>

    <Frame caption="ejemplo de reinicio desde la consola del servidor">
      ![server console restart example](/images/server_restart.gif)
    </Frame>
  </Step>
  <Step title="Revisa ambas consolas">
    Revisa **tanto** la consola de txAdmin (consola del servidor) **como** la consola F8 en el juego, buscando errores.
  </Step>
  <Step title="Compara con errores conocidos">
    Si hay algún error parecido a los de los ejemplos de abajo, tu problema **está causado por el sistema de escrow de assets de FiveM**.
  </Step>
</Steps>

### Ejemplos de errores causados por el sistema de escrow de FiveM

<Frame caption="Solución: ver Error parsing script más abajo">
  ![Escrow error example](/images/error_parsing.png)
</Frame>

<Frame caption="Solución: ver Error parsing script más abajo">
  ![Escrow error example](/images/error_parsing_2.png)
</Frame>

<Frame caption="Solución: ver Failed to verify protected resource más abajo">
  ![Escrow error example](/images/failed_to_verify_protected_resource.png)
</Frame>

<Frame caption="Solución: ver You lack the required entitlement más abajo">
  ![Escrow error example](/images/lack_entitlement.jpg)
</Frame>

## Causas comunes

Estas son las causas más frecuentes de **todos** los errores de escrow de abajo, revísalas primero antes de pasar a las secciones específicas de cada error:

- Estás transfiriendo el archivo del script uno por uno a tu VPS, en lugar de subir el **.zip** y extraerlo **después** de que ya esté en el VPS
- Estás usando **FileZilla** (o tu hosting lo usa) — usa [WinSCP](https://winscp.net/eng/download.php) en su lugar
- La descarga se corrompió — prueba con una instalación limpia y nueva
- Tienes un virus en tu servidor que modifica los archivos del script (muy probable si nada más lo soluciona)

Otros requisitos generales:

- Versión **mínima** de los artifacts del servidor: 4752
- OneSync debe estar activado
- Usa la clave de licencia correcta, generada por la misma cuenta con la que descargaste el script

<Tip>
  Se recomienda **encarecidamente** leer con atención todas las secciones de abajo, ya que estas soluciones han sido probadas por muchos usuarios y deberían funcionar. Si ninguna ayuda, consulta [Qué hacer si nada soluciona los errores](#que-hacer-si-nada-soluciona-los-errores).
</Tip>

Puedes encontrar todos los scripts de jaksam [aquí](https://jaksam1074-fivem-scripts.tebex.io/).

<AccordionGroup>
  <Accordion title="Error parsing script ... <\1>">
    **Ejemplo** de mensaje de error:

    ```text
    Error parsing script @jobs_creator/server/markers/job_shop.lua in resource jobs_creator: @jobs_creator/server/markers/job_shop.lua:1: syntax error near '<\1>'
    ```

    ### Posibles razones

    Además de las [causas comunes](#causas-comunes) de arriba, este error también puede ocurrir si:

    - Puede que tengas que limpiar las cachés del **servidor**

    ### ¿Cómo verifico mi versión de servidor?

    Para verificar qué versión de servidor está usando tu servidor actualmente, usa el siguiente comando en la consola de tu servidor FiveM: `version`

    **Ejemplo**

    <Frame>
      ![version command example](/images/version_example.jpg)
    </Frame>

    ### ¿Cómo actualizo mi versión de servidor?

    Para actualizar tu versión de servidor, descarga los nuevos [artifacts del servidor](https://runtime.fivem.net/artifacts/fivem/build_server_windows/master/) y extráelos, reemplazándolos en la carpeta de tu servidor.

    Esta es la [guía **oficial** de FiveM](https://docs.fivem.net/docs/server-manual/setting-up-a-server/) para actualizar tu servidor.

    ### Mi versión de servidor ya está actualizada, pero sigo teniendo el error

    Si tienes el error aunque tu versión de servidor no sea el problema, revisa [Failed to verify protected resource](#failed-to-verify-protected-resource) más abajo.
  </Accordion>

  <Accordion title="Failed to verify protected resource">
    Ejemplo de mensaje de error:

    ```text
    [svadhesive] Failed to verify protected resource jobs_creator
    ```

    ### Posibles razones

    Además de las [causas comunes](#causas-comunes) de arriba, este error también puede ocurrir si:

    - No tienes un archivo `.fxap` en la carpeta del script

    ### Soluciones

    <Steps>
      <Step title="Vuelve a descargar el script">
        Descarga el script de nuevo desde [FiveM Portal](https://portal.cfx.re/).
      </Step>
      <Step title="Súbelo con WinSCP">
        Sube el script usando [WinSCP](https://winscp.net/eng/download.php) _en lugar de_ FileZilla.
      </Step>
      <Step title="Reinicia el servidor">
        Reinicia el servidor.
      </Step>
    </Steps>
  </Accordion>

  <Accordion title="You lack the required entitlement">
    Ejemplo de mensaje de error:

    ```text
    You lack the required entitlement to use script_name
    ```

    ### Razón

    Todos los scripts que usan el sistema de escrow de FiveM están vinculados a tu cuenta de FiveM (la cuenta que usaste en Tebex).

    Para funcionar, el/los script(s) requieren un servidor que use una server key creada por la misma cuenta de FiveM que usaste en Tebex.

    ### ¿Qué es una server key?

    - La server key se genera en [FiveM Portal](https://portal.cfx.re/)
    - La server key **no** es una clave de script
    - Un servidor de FiveM solo puede usar **1** server key

    **Ejemplo de una server key en server.cfg**

    ```text
    sv_licenseKey "27ztq5g2pcjua67q4xywujkuzh5m7j4a"
    ```

    ### ¿Cómo verifico mi server key?

    Para verificar qué server key está usando tu servidor actualmente, usa el siguiente comando en la consola de tu servidor FiveM: `sv_licenseKey`

    **Ejemplo:**

    <Frame>
      ![sv\_licenseKey example](/images/example_server_key.jpg)
    </Frame>

    ### ¿Cómo verifico si estoy usando la server key correcta?

    <Steps>
      <Step title="Obtén tu server key">
        Usa el comando `sv_licenseKey` en la consola de tu servidor FiveM.
      </Step>
      <Step title="Anota la server key">
        Anota la **server key** que estás usando actualmente.
      </Step>
      <Step title="Abre FiveM Keymaster">
        Ve a [FiveM Portal](https://portal.cfx.re/).
      </Step>
      <Step title="Verifica la propiedad del script">
        Verifica si la cuenta con la que has iniciado sesión en [FiveM Portal](https://portal.cfx.re/) es dueña del/de los script(s) que intentas usar. Si el script no aparece ahí, significa que usaste otra cuenta en Tebex, o que has transferido el script a otra cuenta.

        **Ejemplo con el** [**script Jobs Creator**](https://forum.cfx.re/t/jobs-creator-4-6-esx-in-game-job-creation-menu-without-server-restart/2667762)

        <Frame>
          ![Jobs Creator ownership example](/images/example_purchased_assets.jpg)
        </Frame>
      </Step>
      <Step title="Verifica el propietario de la server key">
        Si la cuenta que usas en [FiveM Portal](https://portal.cfx.re/) es dueña del/de los script(s), verifica si la **server key** que usa tu servidor fue generada por la misma cuenta.

        <Frame>
          ![Server key owner example](/images/keymaster_keys_list.jpg)
        </Frame>
      </Step>
    </Steps>

    ### Mi server key la generó otra persona que no soy yo, ¿qué puedo hacer?

    Tienes 2 opciones:

    - Generar una clave desde tu cuenta y usarla
    - Transferir la propiedad del script a la otra cuenta

    ### ¿Cómo transfiero el script a otra cuenta?

    Para transferir el script a otra cuenta, ve a:

    [FiveM Portal](https://portal.cfx.re/) → pestaña **Assets** → botón rojo **Transfer to another account**

    <Warning>
      cfx.re decidió que los scripts solo se pueden transferir 1 vez, así que no podrás volver a transferir el script.
    </Warning>

    ### Server key de ZAP-Hosting

    Si usas un servidor de Zap-Hosting, **no** tienes que introducir tu server key en server.cfg, sino directamente en su sitio web.

    [Aquí está la guía oficial de ZAP Hosting para esto](https://zap-hosting.com/guides/docs/en/fivem_licensekey/).

    **Captura de ejemplo:**

    <Frame>
      ![ZAP Hosting license key example](/images/zap_hosting_custom_key.png)
    </Frame>
  </Accordion>

  <Accordion title="Qué hacer si nada soluciona los errores">
    ### He seguido todos los pasos pero nada funciona, ¿qué puedo hacer?

    Si has seguido todos los pasos, entonces simplemente tienes un virus en tu servidor. Intenta crear un servidor limpio con solo los scripts por defecto del framework y los scripts de jaksam.

    ### ¿Cómo verifico si tengo un virus en mi servidor?

    Abre el archivo mencionado por el script de jaksam con el **bloc de notas** y desplázate hasta el final. Si hay código parcialmente legible (por ejemplo `local...`), eso es un virus añadido por otra cosa, porque normalmente todo el archivo estaría cifrado. En ese caso, tendrás que resolver ese problema antes de poder usar cualquier script.
  </Accordion>
</AccordionGroup>
