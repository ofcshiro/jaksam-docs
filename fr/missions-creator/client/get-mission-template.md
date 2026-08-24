---
title: "Get a mission template"
description: "Récupère les données d'un template de mission côté client, comme ses options, son label ou sa description."
icon: "clipboard-list"
---

Export pour récupérer un template de mission côté client, au cas où tu voudrais en récupérer les données — par exemple les options, le label, la description, etc.

Un bon exemple d'utilisation est un menu personnalisé qui n'affiche qu'un nombre limité de missions, montrant leur label et description via cet export.

Si tu veux démarrer une mission manuellement après l'avoir sélectionnée, tu peux utiliser l'export [`startMission`](/fr/missions-creator/server/start-mission) pour ça.

```lua Export: getMissionTemplate
exports["missions_creator"]:getMissionTemplate(templateId)
```

#### Paramètres

| Nom         | Type de donnée | Description             |
| ------------ | --------- | -------------------------- |
| `templateId` | integer   | L'ID du template de mission    |

#### Valeur de retour

| Nom           | Type de donnée | Description                                       |
| -------------- | --------- | ---------------------------------------------------- |
| `templateData` | table     | Les données du template de mission. Voir les clés principales ci-dessous       |

##### Clés principales de `templateData`

| Clé           | Type     | Description                                 |
| ------------- | -------- | -------------------------------------------- |
| `id`          | integer  | L'ID du template de mission                       |
| `label`       | string   | Le nom/label de la mission                        |
| `description` | string   | La description de la mission                       |
| `options`     | table    | Table avec les options de la mission (voir ci-dessous)         |

<Note>
  La table `options` contient généralement des champs comme `startCoordinates`, `minPlayers`, `maxPlayers`, `allowedJobs`, `canBeRepeated`, `requiredMissions`.
</Note>
