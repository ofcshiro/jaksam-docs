---
title: "Replace Stash/Safe/Armory"
description: "Utilise ton propre système de stash, de coffre ou d'armurerie à la place de celui par défaut en créant un module stash."
icon: "box"
---

## Comment le remplacer

<Steps>
  <Step title="Aller dans le dossier des modules">
    Va dans le dossier `jobs_creator/_modules`.
  </Step>
  <Step title="Trouver le type de module stash">
    Cherche le module de type **stash** existant à utiliser comme modèle.
  </Step>
  <Step title="Dupliquer le module">
    Copie le module stash existant et colle-le dans le même dossier.
  </Step>
  <Step title="Renommer la copie">
    Renomme la copie collée pour correspondre à ton intégration (ex : `my_stash.lua`).
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
