---
title: "On mission completed"
description: "Se dispara del lado del servidor cuando una misión tiene éxito."
icon: "circle-check"
---

Event que se dispara al completar la misión con éxito.

```lua Event
RegisterNetEvent("missions_creator:missionCompleted", function(instanceId, missionId, players)

end)
```

### Parámetros

| Nombre         | Tipo de dato | Descripción                                       |
| ------------ | --------- | ---------------------------------------------------- |
| `instanceId` | integer   | ID único de la sesión                                     |
| `missionId`  | integer   | ID de la misión, la que ves en el menú de administrador         |
| `players`    | table     | Tabla que contiene a los jugadores que participaron en la misión |

<Note>
  Añade este event en cualquier archivo del lado del servidor en el que quieras usarlo.
</Note>
