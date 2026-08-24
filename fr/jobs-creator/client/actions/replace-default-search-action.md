---
title: "Replace default search action"
description: "Utilise une action de fouille personnalisée à la place de celle par défaut en créant un module search."
icon: "magnifying-glass"
---

Par défaut, l'action de fouille utilise le comportement de fouille intégré de Jobs Creator. Si tu veux utiliser ton propre système de stash, de coffre ou d'armurerie à la place, tu peux le remplacer par un **module** personnalisé.

## Comment le remplacer

<Steps>
  <Step title="Aller dans le dossier des modules">
    Va dans le dossier `jobs_creator/_modules`.
  </Step>
  <Step title="Trouver le type de module search">
    Cherche le module de type **search** existant à utiliser comme modèle.
  </Step>
  <Step title="Dupliquer le module">
    Copie le module search existant et colle-le dans le même dossier.
  </Step>
  <Step title="Renommer la copie">
    Renomme la copie collée pour correspondre à ton intégration (ex : `my_stash_search.lua`).
  </Step>
  <Step title="Ouvrir le fichier">
    Ouvre le fichier fraîchement renommé.
  </Step>
  <Step title="Modifier les events">
    Modifie le contenu du fichier pour qu'il appelle les events/exports de ton propre script de stash, de coffre ou d'armurerie au lieu de ceux par défaut.
  </Step>
  <Step title="Sélectionner le module in-game">
    Ouvre le menu `/jobscreator`, va dans les paramètres, et choisis ton nouveau module pour le job.
  </Step>
</Steps>

<Note>
  Pour plus de détails sur le fonctionnement général des modules, consulte la page [Modules](/fr/jobs-creator/modules).
</Note>
