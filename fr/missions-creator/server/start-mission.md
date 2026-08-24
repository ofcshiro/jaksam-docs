---
title: "Start a mission"
description: "Démarre manuellement une mission côté serveur, par exemple pour l'intégrer à ton propre code."
icon: "play"
---

Export pour démarrer manuellement une mission côté serveur, au cas où tu voudrais l'intégrer à ton code.

```lua Export: startMission
exports["missions_creator"]:startMission(templateId, playerIdOrArray)
```

#### Paramètres

| Nom               | Type de donnée       | Description                                        |
| ------------------ | --------------- | ----------------------------------------------------- |
| `templateId`        | integer         | L'ID du template de mission                                |
| `playerIdOrArray`   | integer \| table | Server ID du joueur, ou un tableau de server IDs      |

#### Valeur de retour

| Nom         | Type de donnée | Description                                                              |
| ------------ | --------- | --------------------------------------------------------------------------- |
| `instanceId` | number    | L'ID d'instance de la mission nouvellement créée, ou `nil` si elle n'a pas pu être créée |
