---
title: "Accesorios de Armas"
icon: "gun"
description: "Mapea múltiples IDs de componentes de arma a un solo ítem de accesorio"
---

## Por qué existe esta guía

En GTA V, cada arma tiene IDs de componente diferentes para el mismo tipo de accesorio. Por ejemplo:

- Un silenciador para una Pistol usa `COMPONENT_AT_PI_SUPP`
- Un silenciador para una Combat Pistol usa `COMPONENT_AT_PI_SUPP_02`

**El sistema de inventario simplifica esto:** Puedes crear UN ítem (como "suppressor") que funcione automáticamente con todas las armas compatibles, mapeando múltiples IDs de componente a él.

## Guía paso a paso

### Paso 1: Comprueba si el ítem ya existe

Primero, comprueba si ya existe un ítem para tu tipo de accesorio en tu base de datos.

<Tabs>
  <Tab title="Armas vanilla de GTA">
    - La mayoría de los accesorios comunes (silenciador, cargador extendido, linterna, etc.) ya deberían existir
    - Usa el comando `/inventory` dentro del juego para comprobar los ítems existentes
  </Tab>
  <Tab title="Armas modificadas">
    - Tendrás que crear un ítem nuevo O agregar el hash de componente del arma modificada a un ítem existente
    - Ejemplo: Si tienes un AK47 modificado con silenciador, puedes agregar su hash de silenciador al ítem "suppressor" existente
  </Tab>
</Tabs>

**Crear/Editar el ítem:**

<Steps>
  <Step title="Abre la UI de gestión del inventario">
    Escribe `/inventory` dentro del juego.
  </Step>
  <Step title="Crea o edita un ítem">
    Crea un ítem nuevo o edita uno existente.
  </Step>
  <Step title="Configura el tipo de ítem correcto">
    <CardGroup cols={2}>
      <Card title="barrel">
        Silenciadores, frenos de boca
      </Card>

      <Card title="clip">
        Cargadores
      </Card>

      <Card title="scope">
        Miras y ópticas
      </Card>

      <Card title="flashlight">
        Linternas tácticas
      </Card>

      <Card title="grip">
        Empuñaduras delanteras
      </Card>
    </CardGroup>

    <Frame caption="Ejemplo con el silenciador predeterminado">
      ![Ejemplo de edición del componente del ítem silenciador predeterminado](/images/weapon-attachments-item-example.jpg)
    </Frame>
  </Step>
</Steps>

### Paso 2: Agrega los hashes de componente

Ahora necesitas agregar el/los hash(es) de componente a los que este ítem debería aplicarse en las armas.

**Dónde encontrar los hashes de componente:**

<Tabs>
  <Tab title="Armas vanilla de GTA">
    - Revisa la [wiki](https://docs.fivem.net/docs/game-references/weapon-models/)
    - O busca en internet "GTA V weapon components list"
  </Tab>
  <Tab title="Armas modificadas">
    - Lo más probable es que tu script de arma modificada contenga un archivo de texto con los hashes de componente
    - Un ejemplo de nombres de componente es que suelen empezar con `COMPONENT_`
    - Contacta al creador del arma o consulta su documentación si no lo encuentras
  </Tab>
</Tabs>

**Cómo agregarlos:**

<Steps>
  <Step title="Abre la sección de Hashes de Componente">
    En la pantalla de edición del ítem de accesorio, busca la sección "Component Hashes".
  </Step>
  <Step title="Agrega un hash">
    Haz clic en "Add Component Hash".
  </Step>
  <Step title="Ingresa el hash">
    Ingresa el hash de componente (p. ej., `COMPONENT_AT_PI_SUPP`).
  </Step>
  <Step title="Repite">
    Repite para todos los componentes con los que quieras que funcione este accesorio.
  </Step>
</Steps>

<Info>
  El menú te mostrará qué armas son compatibles con cada hash de componente que agregues.
</Info>

<Frame caption="Ejemplo de la lista de hashes de un ítem">
  ![Ejemplo de la lista de hashes de un ítem](/images/weapon-attachments-hashes-example.jpg)
</Frame>

### Paso 3: Prueba dentro del juego

<Steps>
  <Step title="Dáte el ítem a ti mismo">
    `/giveitem [your_id] [item_name] 1` o mediante el omnipack (`F1` con el inventario abierto).
  </Step>
  <Step title="Dáte un arma a ti mismo">
    Dáte un arma compatible.
  </Step>
  <Step title="Colócalo">
    Intenta colocar el componente.
  </Step>
</Steps>

<Tip>
  ¡Eso es todo! El sistema aplicará automáticamente el componente correcto según el arma.
</Tip>

## Ejemplo completo

Digamos que quieres agregar un silenciador para un arma modificada llamada "WEAPON_MODDEDAK47":

<Steps>
  <Step title="Comprueba los ítems existentes">
    Abre `/inventory` y busca "suppressor" - ¡ya existe!
  </Step>
  <Step title="Edita el ítem">
    Haz clic en editar sobre el ítem suppressor.
  </Step>
  <Step title="Agrega el hash">
    Agrega `COMPONENT_MODDEDAK47_SUPP` a la lista de hashes de componente.
  </Step>
  <Step title="Guarda">
    Guarda el ítem.
  </Step>
  <Step title="Prueba">
    Dáte el suppressor y el AK47 modificado, luego intenta colocarlo.
  </Step>
</Steps>
