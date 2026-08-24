---
title: "Metadatos"
icon: "tags"
description: "Muestra metadatos de ítems a los jugadores y configura valores de metadatos predeterminados o dinámicos"
---

## Cómo mostrar metadatos a los jugadores

Mostrar metadatos específicos a los jugadores es fácil. Antes que nada, necesitas saber cuál es la clave del metadato que quieres mostrar. Para eso, puedes activar el "Debug mode" en el menú de settings de `/inventory`, y luego pasar el cursor sobre el ítem del que quieres ver los metadatos.

<Columns cols={2}>
  <Frame>
    ![Captura de pantalla de la configuración de debug del ítem](/images/metadata-debug-settings.png)
  </Frame>

  <Frame>
    ![Captura de pantalla de los metadatos de debug del ítem](/images/metadata-debug-item.png)
  </Frame>
</Columns>

### Agregarlo a un ítem individual

Para mostrar a los jugadores los metadatos de un solo ítem, puedes agregar y adaptar este código en la definición de ese ítem, en el archivo `jaksam_inventory/_data/items.lua`:

```lua
displayFields = {
    { field = 'YOUR_METADATA_KEY_HERE', label = 'TEXT YOU WANT HERE: ${value}'}, -- Ejemplo aleatorio
    { field = 'ammo', label = 'Ammo: ${value}'}, -- Útil en armas (ya viene integrado por defecto)
    { field = 'plate', label = 'Plate: ${value}'}, -- Útil en llaves de vehículos
},
```

<Frame>
  ![Ejemplo de campos de visualización de un ítem individual](/images/metadata-single-item-example.png)
</Frame>

### Agregarlo a todos los tipos de ítem

Para mostrar a los jugadores los metadatos de un tipo de ítem completo, el método es exactamente el mismo, pero colócalo en la tabla `Script.defaultsByType`, en el archivo `jaksam_inventory/_data/defaults.lua`.

### Opcional: Hacer que los valores de metadatos se vean mejor

A veces quieres mostrar los metadatos de una forma más agradable a los jugadores. Por ejemplo, en lugar de mostrar "weapon_pistol", quieres mostrar "Pistol". ¡Aquí es donde entran los formatters!

<Tip>
  Un formatter es como un traductor: toma el valor original (p. ej. `weapon_pistol`) y lo convierte en algo más agradable (p. ej. `Pistol`).
</Tip>

Puedes usar formatters integrados o crear los tuyos propios en `jaksam_inventory/_data/formatter.lua`. Así se usan:

```lua
displayFields = {
    { field = 'item', label = 'Label: ${value}', formatterId = "itemNameToLabel"}, -- Un ejemplo con un formatter integrado
},
```

## Cómo configurar metadatos predeterminados para ítems

¿Quieres que los ítems tengan ciertos valores de metadatos cuando se crean por primera vez? Por ejemplo, tal vez quieras que las armas nuevas empiecen con 50% de durabilidad. Así se hace:

<Steps>
  <Step title="Abre el menú de admin">
    Escribe `/inventory` dentro del juego para abrir el menú de admin.
  </Step>
  <Step title="Busca el ítem">
    Busca y haz clic en el ítem que quieres editar.
  </Step>
  <Step title="Abre la pestaña de metadatos">
    Haz clic en la pestaña "metadata".
  </Step>
  <Step title="Configura los valores">
    Configura los valores de metadatos que quieras.
  </Step>
</Steps>

### Avanzado - Usar templates para metadatos dinámicos

A veces quieres metadatos que cambien según ciertas condiciones. Para esto, puedes usar templates:

<Steps>
  <Step title="Abre la pestaña de metadatos">
    Ve a la misma pestaña de metadatos en el editor de ítems.
  </Step>
  <Step title="Cambia al tipo template">
    Cambia el tipo de metadato a `template`.
  </Step>
  <Step title="Elige o crea un template">
    Puedes seleccionar un template existente, o crear el tuyo propio en `jaksam_inventory/_data/metadata_templates.lua`.
  </Step>
</Steps>

¡Los templates te permiten crear metadatos que se actualizan automáticamente según las reglas que definas!

#### Ejemplo

Algunos ejemplos de lo que puedes hacer con templates de metadatos dinámicos:

- Asignar a la cédula de identidad de un jugador su nombre, fecha de nacimiento, altura, etc.
- Asignar una durabilidad aleatoria a un arma
- Asignar la fecha de creación a un ítem (la primera vez que se crea el ítem)
