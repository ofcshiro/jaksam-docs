---
title: "Get a mission template"
description: "Recupera los datos de una plantilla de misión del lado del cliente, como sus opciones, etiqueta o descripción."
icon: "clipboard-list"
---

Export para obtener una plantilla de misión del lado del cliente, en caso de que quieras recuperar sus datos — por ejemplo opciones, etiqueta, descripción, etc.

Un buen ejemplo de uso es un menú personalizado que muestra solo un número limitado de misiones, mostrando su etiqueta y descripción mediante este export.

Si quieres iniciar una misión manualmente después de seleccionarla, puedes usar el [export `startMission`](/es/missions-creator/server/start-mission) para hacerlo.

```lua Export: getMissionTemplate
exports["missions_creator"]:getMissionTemplate(templateId)
```

#### Parámetros

| Nombre         | Tipo de dato | Descripción             |
| ------------ | --------- | -------------------------- |
| `templateId` | integer   | El ID de la plantilla de misión    |

#### Valor de retorno

| Nombre           | Tipo de dato | Descripción                                       |
| -------------- | --------- | ---------------------------------------------------- |
| `templateData` | table     | Los datos de la plantilla de misión. Ver las claves principales abajo       |

##### Claves principales de `templateData`

| Clave           | Tipo     | Descripción                                 |
| ------------- | -------- | -------------------------------------------- |
| `id`          | integer  | El ID de la plantilla de misión                       |
| `label`       | string   | El nombre/etiqueta de la misión                        |
| `description` | string   | La descripción de la misión                       |
| `options`     | table    | Tabla con las opciones de la misión (ver abajo)         |

<Note>
  La tabla `options` normalmente contiene campos como `startCoordinates`, `minPlayers`, `maxPlayers`, `allowedJobs`, `canBeRepeated`, `requiredMissions`.
</Note>
