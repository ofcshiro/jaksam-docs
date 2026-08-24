---
title: "Installation"
description: "Installe Vehicles Keys sur ton serveur FiveM avec ESX ou QBCore, y compris la configuration optionnelle des items par défaut."
icon: "download"
---

L'installation du script est extrêmement simple.

## Prérequis

- **ESX** ou **QBCore**
- Le [script de crochetage](https://github.com/baguscodestudio/lockpick) de [baguscodestudio](https://github.com/baguscodestudio/lockpick)
- Sur QBCore, le script [`menu_default`](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing)

<Danger>
  N'utilise **PAS** FileZilla pour envoyer les fichiers, sinon le script ne fonctionnera **PAS**.

  Utilise [WinSCP](https://winscp.net/eng/download.php) à la place.
</Danger>

<Tabs>
  <Tab title="ESX">
    <Steps>
      <Step title="Télécharger et extraire">
        Télécharge le script et extrais-le dans tes resources.
      </Step>
      <Step title="Ajouter au démarrage automatique">
        Ajoute le script à ton démarrage automatique (exemple : `server.cfg`).
      </Step>
      <Step title="Configuration de la base de données">
        Le script configure **automatiquement** la base de données. Si ce n'est pas le cas, tu peux exécuter manuellement les fichiers du dossier `vehicles_keys/sql/`.
      </Step>
      <Step title="Script de crochetage">
        Télécharge et démarre le [script de crochetage](https://github.com/baguscodestudio/lockpick) _(crédits à [baguscodestudio](https://github.com/baguscodestudio/lockpick))_.
      </Step>
    </Steps>

    ### Ajouter les items — Optionnel

    Pour ajouter les items prêts à l'emploi, il te suffit d'exécuter le fichier `vehicles_keys/sql/items_limit.sql` **ou** `vehicles_keys/sql/items_weight.sql`, selon que ton serveur utilise le limit ou le weight.

    <Info>
      La dernière version d'ESX utilise le **weight**.
    </Info>

    <Danger>
      Si ça ne fonctionne pas, assure-toi d'utiliser la dernière version officielle d'ESX avec les dépendances requises.
    </Danger>
  </Tab>
  <Tab title="QBCore">
    <Steps>
      <Step title="Télécharger et extraire">
        Télécharge le script et extrais-le dans tes resources.
      </Step>
      <Step title="Ajouter au démarrage automatique">
        Ajoute le script à ton démarrage automatique (exemple : `server.cfg`).
      </Step>
      <Step title="Configuration de la base de données">
        Le script configure **automatiquement** la base de données. Si ce n'est pas le cas, tu peux exécuter manuellement les fichiers du dossier `vehicles_keys/sql/`.
      </Step>
      <Step title="Script de crochetage">
        Télécharge et démarre le [script de crochetage](https://github.com/baguscodestudio/lockpick) _(crédits à [baguscodestudio](https://github.com/baguscodestudio/lockpick))_.
      </Step>
      <Step title="Installer menu_default">
        Télécharge et extrais le script [menu_default](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing) dans tes resources, **sans le renommer**, et ajoute-le à ton démarrage automatique (exemple : `server.cfg`).
      </Step>
    </Steps>

    ### Ajouter les items — Optionnel

    Pour ajouter les nouveaux items, édite le fichier `qb-core/shared/items.lua` et ajoute le code suivant à la fin de la table :

    ```lua
    -- Items de Vehicles Keys
    ['vehicle_alarm_1'] = {['name'] = 'vehicle_alarm_1', ['label'] = 'Vehicle alarm level 1', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Vehicle alarm level 1'},
    ['vehicle_alarm_2'] = {['name'] = 'vehicle_alarm_2', ['label'] = 'Vehicle alarm level 2', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Vehicle alarm level 2'},
    ['vehicle_alarm_3'] = {['name'] = 'vehicle_alarm_3', ['label'] = 'Vehicle alarm level 3', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Vehicle alarm level 3'},
    ['vehicle_alarm_4'] = {['name'] = 'vehicle_alarm_4', ['label'] = 'Vehicle alarm level 4', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Vehicle alarm level 4'},
    ['vehicle_transfer_contract'] = {['name'] = 'vehicle_transfer_contract', ['label'] = 'Vehicle transfer contract', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Used to sell your vehicle to someone'},
    ```

    <Frame caption="Exemple de capture d'écran">
      ![QBCore Vehicles Keys items example](/images/qb_core_vehicles_keys_items.png)
    </Frame>
  </Tab>
</Tabs>

Tu es prêt ! Profite bien du script 😁

## Vérification

<Info>
  [TODO: INFORMATION NEEDED] Aucune vérification en jeu d'une installation réussie n'est encore documentée pour Vehicles Keys.
</Info>

## Étape optionnelle

Une fois la base de données correctement configurée, tu peux supprimer les fichiers du dossier `vehicles_keys/sql/`, afin que le script n'essaie plus de la configurer à chaque démarrage.
