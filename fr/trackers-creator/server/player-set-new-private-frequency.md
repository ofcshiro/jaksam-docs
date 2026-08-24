---
title: "Joueur a défini une nouvelle fréquence privée"
description: "Se déclenche côté serveur quand un joueur définit une nouvelle fréquence de tracker privée."
icon: "sliders"
---

Cet event se déclenche quand un joueur utilise l'item de tracker privé et définit une nouvelle fréquence.

```lua Event
AddEventHandler("trackers_creator:playerSetNewPrivateFrequency", function(playerId, trackerId)

end)
```

### Paramètres

| Nom        | Type de donnée | Description                 |
| ----------- | --------- | ------------------------------ |
| `playerId`  | integer   | Le server ID du joueur     |
| `frequency` | integer   | Nouvelle fréquence choisie            |
