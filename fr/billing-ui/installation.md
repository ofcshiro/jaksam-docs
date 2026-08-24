---
title: "Installation"
description: "Installe Billing UI sur ton serveur FiveM avec ESX ou QBCore."
icon: "download"
---

L'installation du script est extrêmement simple.

## Prérequis

- **ESX** ou **QBCore**
- Sur ESX, `esx_billing` doit être retiré (voir l'avertissement ci-dessous)
- Sur QBCore, le script [`menu_default`](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing)

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
      <Step title="Ajoute à l'auto start">
        Ajoute le script dans ton auto start (exemple : `server.cfg`).
      </Step>
      <Step title="Configuration de la base de données">
        Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `billing_ui/sql/`.
      </Step>
      <Step title="Configure les options">
        Configure les options dans les fichiers de config (lis bien les commentaires, ils expliquent tout).
      </Step>
    </Steps>

    <Warning>
      Assure-toi de retirer `esx_billing` pour éviter des problèmes.
    </Warning>
  </Tab>
  <Tab title="QBCore">
    <Steps>
      <Step title="Télécharge et extrais">
        Télécharge le script et extrais-le dans tes resources.
      </Step>
      <Step title="Ajoute à l'auto start">
        Ajoute le script dans ton auto start (exemple : `server.cfg`).
      </Step>
      <Step title="Configuration de la base de données">
        Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `billing_ui/sql/`.
      </Step>
      <Step title="Configure les options">
        Configure les options dans les fichiers de config (lis bien les commentaires, ils expliquent tout).
      </Step>
      <Step title="Installe menu_default">
        Télécharge et extrais le script [menu_default](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing) dans tes resources, **sans le renommer**, et ajoute-le à ton auto start (exemple : `server.cfg`).
      </Step>
    </Steps>
  </Tab>
</Tabs>

Tu es prêt ! Profite bien du script 😁

## Vérification

<Info>
  \[TODO : INFORMATION NÉCESSAIRE\] Aucune vérification in-game pour une installation réussie n'est encore documentée pour Billing UI.
</Info>

## Étape optionnelle

Une fois la base de données correctement configurée, tu peux supprimer les fichiers du dossier `billing_ui/sql/`, pour que le script n'essaie pas de la configurer à nouveau à chaque démarrage.
