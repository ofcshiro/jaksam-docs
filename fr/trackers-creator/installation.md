---
title: "Installation"
description: "Installe Trackers Creator sur ton serveur FiveM avec ESX ou QBCore, incluant la configuration optionnelle des items par défaut."
icon: "download"
---

L'installation du script est extrêmement simple.

## Prérequis

- **ESX** ou **QBCore**

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
        Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `trackers_creator/sql/`.
      </Step>
    </Steps>

    ### Ajouter les items — Optionnel

    Pour ajouter les items prédéfinis, il te suffit d'exécuter le fichier `trackers_creator/sql/items_limit.sql` **ou** `trackers_creator/sql/items_weight.sql`, selon que ton serveur utilise limit ou weight.

    <Info>
      La dernière version d'ESX utilise **weight**.
    </Info>

    <Danger>
      Si ça ne fonctionne pas, assure-toi d'utiliser la dernière version officielle d'ESX avec les dépendances nécessaires.
    </Danger>
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
        Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `trackers_creator/sql/`.
      </Step>
    </Steps>

    ### Ajouter les items — Optionnel

    Pour ajouter les nouveaux items, modifie le fichier `qb-core/shared/items.lua` et ajoute le code suivant en bas de la table :

    ```lua
    ['tracker_sender'] = {['name'] = 'tracker_sender', ['label'] = 'Tracker sender', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['tracker_receiver'] = {['name'] = 'tracker_receiver', ['label'] = 'Tracker receiver', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['private_tracker'] = {['name'] = 'private_tracker', ['label'] = 'Private tracker', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil},
    ```
  </Tab>
</Tabs>

Tu es prêt ! Profite bien du script 😁

## Vérification

<Info>
  \[TODO : INFORMATION NÉCESSAIRE\] Aucune vérification in-game pour une installation réussie n'est encore documentée pour Trackers Creator.
</Info>

## Étape optionnelle

Une fois la base de données correctement configurée, tu peux supprimer les fichiers du dossier `trackers_creator/sql/`, pour que le script n'essaie pas de la reconfigurer à chaque démarrage.
