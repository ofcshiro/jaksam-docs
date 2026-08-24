---
title: "On mission failed"
description: "Se dispara del lado del servidor cuando falla una misión."
icon: "circle-xmark"
---

Event que se dispara cuando falla la misión.

```lua Event
RegisterNetEvent("missions_creator:missionFailed", function(instanceId, missionId, players, reason)

end)
```

### Parámetros

| Nombre         | Tipo de dato | Descripción                                       |
| ------------ | --------- | ---------------------------------------------------- |
| `instanceId` | integer   | ID único de la sesión                                     |
| `missionId`  | integer   | ID de la misión, la que ves en el menú de administrador         |
| `players`    | table     | Tabla que contiene a los jugadores que participaron en la misión |
| `reason`     | string    | El motivo por el que falló la misión                     |

<Note>
  Añade este event en cualquier archivo del lado del servidor en el que quieras usarlo.
</Note>
