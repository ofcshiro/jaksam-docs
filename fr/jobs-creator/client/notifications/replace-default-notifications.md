---
title: "Remplacer les notifications"
description: "Utilise un système de notifications personnalisé à la place du système par défaut en créant un module notify."
icon: "bell"
---

Sert à afficher les notifications normales, par exemple `"You are not on duty"`. Ce sont les notifications normales, pas le TextUI, mais le processus est le même pour les deux.

## Comment le remplacer

<Steps>
  <Step title="Va dans le dossier des modules">
    Va dans le dossier `jobs_creator/_modules`.
  </Step>
  <Step title="Trouve le type de module notify">
    Cherche le module de type **notify** existant à utiliser comme modèle.
  </Step>
  <Step title="Duplique le module">
    Copie le module notify existant et colle-le dans le même dossier.
  </Step>
  <Step title="Renomme la copie">
    Renomme la copie collée pour qu'elle corresponde à ton intégration (par exemple `my_notify.lua`).
  </Step>
  <Step title="Ouvre le fichier">
    Ouvre le fichier fraîchement renommé.
  </Step>
  <Step title="Modifie les events">
    Modifie le contenu du fichier pour qu'il appelle les events/exports de ton propre script de notification au lieu de ceux par défaut.
  </Step>
  <Step title="Sélectionne le module in-game">
    Ouvre le menu `/jobscreator`, va dans les paramètres, et choisis ton nouveau module pour le job.
  </Step>
</Steps>

<Note>
  Pour plus de détails sur le fonctionnement général des modules, consulte la page [Modules](/fr/jobs-creator/modules).
</Note>
