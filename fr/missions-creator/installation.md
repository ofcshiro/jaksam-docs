---
title: "Installation"
description: "Installe Missions Creator sur ton serveur FiveM avec ESX ou QBCore, incluant des scripts de minijeux optionnels."
icon: "download"
---

L'installation du script est extrêmement simple.

## Prérequis

- **ESX** ou **QBCore**
- `jaksam_core`, démarré avant `missions_creator`
- Scripts de minijeux optionnels (voir la dernière étape ci-dessous) si tu veux les utiliser

<Danger>
  N'utilise **PAS** FileZilla pour uploader les fichiers, sinon le script ne fonctionnera **PAS**.

  Utilise [WinSCP](https://winscp.net/eng/download.php) à la place.
</Danger>

<Tabs>
  <Tab title="ESX">
    <Steps>
      <Step title="Télécharge et extrais">
        Télécharge le script et extrais-le dans tes resources.
      </Step>
      <Step title="Télécharge jaksam_core">
        Télécharge `jaksam_core` et extrais-le dans tes resources.
      </Step>
      <Step title="Ajoute jaksam_core à l'auto start">
        Ajoute `jaksam_core` dans ton auto start (exemple : `server.cfg`).
      </Step>
      <Step title="Ajoute missions_creator à l'auto start">
        Démarre `missions_creator` **après** `jaksam_core`.
      </Step>
      <Step title="Configuration de la base de données">
        Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `missions_creator/sql/`.
      </Step>
      <Step title="Scripts de minijeux optionnels">
        - Télécharge et démarre le [script de minijeu datacrack](https://github.com/utkuali/datacrack) _(crédits à [utkuali](https://github.com/utkuali))_
        - Télécharge et démarre le [script de minijeu d'empreintes digitales](https://github.com/utkuali/Finger-Print-Hacking-Game) _(crédits à [utkuali](https://github.com/utkuali))_
        - Télécharge et démarre le [script de minijeu de mémoire](https://github.com/ultrahacx/ultra-keypackhack) _(crédits à [ultrahacx](https://github.com/ultrahacx))_
      </Step>
    </Steps>

    <Danger>
      Si ça ne fonctionne pas, assure-toi d'utiliser la dernière version officielle d'ESX avec les dépendances nécessaires.
    </Danger>
  </Tab>
  <Tab title="QBCore">
    <Steps>
      <Step title="Télécharge et extrais">
        Télécharge le script et extrais-le dans tes resources.
      </Step>
      <Step title="Télécharge jaksam_core">
        Télécharge `jaksam_core` et extrais-le dans tes resources.
      </Step>
      <Step title="Ajoute jaksam_core à l'auto start">
        Ajoute `jaksam_core` dans ton auto start (exemple : `server.cfg`).
      </Step>
      <Step title="Ajoute missions_creator à l'auto start">
        Démarre `missions_creator` **après** `jaksam_core`.
      </Step>
      <Step title="Configuration de la base de données">
        Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `missions_creator/sql/`.
      </Step>
      <Step title="Scripts de minijeux optionnels">
        - Télécharge et démarre le [script de minijeu datacrack](https://github.com/utkuali/datacrack) _(crédits à [utkuali](https://github.com/utkuali))_
        - Télécharge et démarre le [script de minijeu d'empreintes digitales](https://github.com/utkuali/Finger-Print-Hacking-Game) _(crédits à [utkuali](https://github.com/utkuali))_
        - Télécharge et démarre le [script de minijeu de mémoire](https://github.com/ultrahacx/ultra-keypackhack) _(crédits à [ultrahacx](https://github.com/ultrahacx))_
      </Step>
    </Steps>
  </Tab>
</Tabs>

Tu es prêt ! Profite bien du script 😁

## Vérification

<Info>
  \[TODO : INFORMATION NÉCESSAIRE\] La documentation existante mentionne un menu admin in-game (les missions font référence à leur ID "celui que tu vois dans le menu admin") mais n'indique pas la commande pour l'ouvrir. À ajouter ici une fois confirmé.
</Info>

## Étape optionnelle

Une fois la base de données correctement configurée, tu peux supprimer les fichiers du dossier `missions_creator/sql/`, pour que le script n'essaie pas de la configurer à nouveau à chaque démarrage.
