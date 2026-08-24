---
title: "On mission completed"
description: "Se déclenche côté serveur quand une mission réussit."
icon: "circle-check"
---

Event déclenché à la réussite d'une mission.

```lua Event
RegisterNetEvent("missions_creator:missionCompleted", function(instanceId, missionId, players)

end)
```

### Paramètres

| Nom         | Type de donnée | Description                                       |
| ------------ | --------- | ---------------------------------------------------- |
| `instanceId` | integer   | ID unique de session                                     |
| `missionId`  | integer   | ID de la mission, celui que tu vois dans le menu admin         |
| `players`    | table     | Table contenant les joueurs qui ont participé à la mission |

<Note>
  Ajoute cet event dans n'importe quel fichier côté serveur dans lequel tu veux l'utiliser.
</Note>
