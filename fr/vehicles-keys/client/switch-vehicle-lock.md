---
title: "Switch vehicle lock"
description: "Change le verrou d'un véhicule, en révoquant les clés précédemment partagées par le propriétaire."
icon: "key"
---

Déclencher cet event (depuis le côté client) changera le verrou du véhicule ayant cette plaque, en retirant toutes les clés précédemment partagées par le propriétaire à d'autres joueurs.

```lua Event
TriggerServerEvent("vehicles_keys:switchLock", plate)
```

### Paramètres

| Nom    | Type de donnée | Description                |
| ------- | --------- | ------------------------------ |
| `plate` | string    | La plaque du véhicule          |
