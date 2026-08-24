---
title: "On mission failed"
description: "Se déclenche côté serveur quand une mission échoue."
icon: "circle-xmark"
---

Event déclenché à l'échec d'une mission.

```lua Event
RegisterNetEvent("missions_creator:missionFailed", function(instanceId, missionId, players, reason)

end)
```

### Paramètres

| Nom         | Type de donnée | Description                                       |
| ------------ | --------- | ---------------------------------------------------- |
| `instanceId` | integer   | ID unique de session                                     |
| `missionId`  | integer   | ID de la mission, celui que tu vois dans le menu admin         |
| `players`    | table     | Table contenant les joueurs qui ont participé à la mission |
| `reason`     | string    | La raison de l'échec de la mission                     |

<Note>
  Ajoute cet event dans n'importe quel fichier côté serveur dans lequel tu veux l'utiliser.
</Note>
