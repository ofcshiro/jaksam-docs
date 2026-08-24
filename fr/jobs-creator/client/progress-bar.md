---
title: "Progress bar"
description: "Remplace la barre de progression par défaut par la tienne, ou utilise celle intégrée dans des scripts externes."
icon: "spinner"
---

## Comment la remplacer

Tu peux utiliser un [module](/fr/jobs-creator/modules) Jobs Creator si tu veux utiliser ta propre barre de progression.

<Steps>
  <Step title="Aller dans le dossier des modules">
    Va dans le dossier `jobs_creator/_modules`.
  </Step>
  <Step title="Trouver le type de module progressbar">
    Cherche le module de type **progressbar** existant à utiliser comme modèle.
  </Step>
  <Step title="Dupliquer le module">
    Copie le module progressbar existant et colle-le dans le même dossier.
  </Step>
  <Step title="Renommer la copie">
    Renomme la copie collée pour correspondre à ton intégration (ex : `my_progressbar.lua`).
  </Step>
  <Step title="Ouvrir le fichier">
    Ouvre le fichier fraîchement renommé.
  </Step>
  <Step title="Modifier les events">
    Modifie le contenu du fichier pour qu'il appelle les events/exports de ta propre barre de progression au lieu de celle par défaut.
  </Step>
  <Step title="Sélectionner le module in-game">
    Ouvre le menu `/jobscreator`, va dans les paramètres, et choisis ton nouveau module pour le job.
  </Step>
</Steps>

## Utilisation dans des scripts externes

Si tu aimes la barre de progression par défaut du script et que tu veux l'utiliser dans des scripts externes, voici l'event :

<CodeGroup>

```lua Event
TriggerEvent("jobs_creator:startProgressBar", timeInMS, text, hexColor)
```

```lua Example
-- This will create a command to show a red progressbar
-- /progressbar 5000 Hello
RegisterCommand("progressbar", function(playerId, args)
    TriggerEvent("jobs_creator:startProgressBar", tonumber(args[1]), args[2], "#ff0000")
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `timeInMS` | integer | Durée de la barre de progression en millisecondes |
| `text` | string | Le texte qui sera affiché avec la barre de progression |
| `hexColor` | string | La couleur de la barre de progression en code hexadécimal (exemple `#70f2b4`). Peut être `nil` pour utiliser celle par défaut du script |
