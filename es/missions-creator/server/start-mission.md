---
title: "Start a mission"
description: "Inicia manualmente una misión del lado del servidor, por ejemplo para integrarla con tu propio código."
icon: "play"
---

Export para iniciar manualmente una misión del lado del servidor, en caso de que quieras integrarla con tu código.

```lua Export: startMission
exports["missions_creator"]:startMission(templateId, playerIdOrArray)
```

#### Parámetros

| Nombre               | Tipo de dato       | Descripción                                        |
| ------------------ | --------------- | ----------------------------------------------------- |
| `templateId`        | integer         | El ID de la plantilla de misión                                |
| `playerIdOrArray`   | integer \| table | ID de servidor del jugador, o un array de IDs de servidor de jugadores      |

#### Valor de retorno

| Nombre         | Tipo de dato | Descripción                                                              |
| ------------ | --------- | --------------------------------------------------------------------------- |
| `instanceId` | number    | El ID de instancia de la misión recién creada, o `nil` si no se pudo crear |
