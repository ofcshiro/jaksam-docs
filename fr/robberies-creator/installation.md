---
title: "Installation"
description: "Installe Robberies Creator sur ton serveur FiveM avec ESX, QBCore ou OX Inventory, incluant des scripts de minijeux optionnels et la configuration des items par défaut."
icon: "download"
---

L'installation du script est extrêmement simple.

## Prérequis

- **ESX**, **QBCore**, ou **OX Inventory**
- Le [script de coffre-fort](https://github.com/VHall1/pd-safe) de [VHall1](https://github.com/VHall1)
- Le [script de crochetage](https://github.com/baguscodestudio/lockpick) de [baguscodestudio](https://github.com/baguscodestudio/lockpick)
- Scripts de minijeux optionnels (voir ci-dessous) si tu veux les utiliser

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
        Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `robberies_creator/sql/`.
      </Step>
      <Step title="Script de coffre-fort">
        Télécharge et démarre le [script de coffre-fort](https://github.com/VHall1/pd-safe) _(crédits à [VHall1](https://github.com/VHall1))_.
      </Step>
      <Step title="Script de crochetage">
        Télécharge et démarre le [script de crochetage](https://github.com/baguscodestudio/lockpick) _(crédits à [baguscodestudio](https://github.com/baguscodestudio/lockpick))_.
      </Step>
      <Step title="Scripts de minijeux optionnels">
        - Télécharge et démarre le [script de minijeu datacrack](https://github.com/utkuali/datacrack) _(crédits à [utkuali](https://github.com/utkuali))_
        - Télécharge et démarre le [script de minijeu d'empreintes digitales](https://github.com/utkuali/Finger-Print-Hacking-Game) _(crédits à [utkuali](https://github.com/utkuali))_
        - Télécharge et démarre le [script de minijeu de mémoire](https://github.com/ultrahacx/ultra-keypackhack) _(crédits à [ultrahacx](https://github.com/ultrahacx))_
      </Step>
    </Steps>

    ### Ajouter les items — Optionnel

    Pour ajouter les items prédéfinis, il te suffit d'exécuter le fichier `robberies_creator/sql/items_limit.sql` **ou** `robberies_creator/sql/items_weight.sql`, selon que ton serveur utilise limit ou weight.

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
        Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `robberies_creator/sql/`.
      </Step>
      <Step title="Script de coffre-fort">
        Télécharge et démarre le [script de coffre-fort](https://github.com/VHall1/pd-safe) _(crédits à [VHall1](https://github.com/VHall1))_.
      </Step>
      <Step title="Script de crochetage">
        Télécharge et démarre le [script de crochetage](https://github.com/baguscodestudio/lockpick) _(crédits à [baguscodestudio](https://github.com/baguscodestudio/lockpick))_.
      </Step>
      <Step title="Scripts de minijeux optionnels">
        - Télécharge et démarre le [script de minijeu datacrack](https://github.com/utkuali/datacrack) _(crédits à [utkuali](https://github.com/utkuali))_
        - Télécharge et démarre le [script de minijeu d'empreintes digitales](https://github.com/utkuali/Finger-Print-Hacking-Game) _(crédits à [utkuali](https://github.com/utkuali))_
        - Télécharge et démarre le [script de minijeu de mémoire](https://github.com/ultrahacx/ultra-keypackhack) _(crédits à [ultrahacx](https://github.com/ultrahacx))_
      </Step>
    </Steps>

    ### Ajouter les items — Optionnel

    Pour ajouter les nouveaux items, modifie le fichier `qb-core/shared/items.lua` et ajoute le code suivant en bas de la table :

    ```lua
    -- Items de Robberies Creator
    ['hacking_computer'] = {['name'] = 'hacking_computer', ['label'] = 'Hacking computer', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Computer to hack panels'},
    ['thermal_charge'] = {['name'] = 'thermal_charge', ['label'] = 'Thermal charge', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Use to melt some doors'},
    ['gas_mask'] = {['name'] = 'gas_mask', ['label'] = 'Gas mask', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Protects from lethal gas'},
    ['drill'] = {['name'] = 'drill', ['label'] = 'Drill', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Can be used to open trucks doors'},
    ['gold_ingot'] = {['name'] = 'gold_ingot', ['label'] = 'Gold ingot', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Goooold'},
    ['diamonds_box'] = {['name'] = 'diamonds_box', ['label'] = 'Diamond box', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Diamooonds'},
    ['lockpick'] = {['name'] = 'lockpick', ['label'] = 'Lockpick', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Used to lockpick doors'},
    ['painting'] = {['name'] = 'painting', ['label'] = 'Painting', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil, ['description'] = 'Expensive painting'},
    ```

    <Frame caption="Exemple de capture d'écran">
      ![QBCore Robberies Creator items example](/images/qb_core_robberies_creator_items.png)
    </Frame>
  </Tab>
  <Tab title="OX Inventory">
    Voici une liste d'items à utiliser avec OX Inventory. Tu peux même l'utiliser avec l'inventaire de jaksam, dans le paramètre "import from code".

    ```lua
    ['hacking_computer'] = {
        label = 'Hacking computer',
        weight = 500,
        stack = true,
        close = true,
        description = 'Computer to hack panels'
    },

    ['thermal_charge'] = {
        label = 'Thermal charge',
        weight = 500,
        stack = true,
        close = true,
        description = 'Use to melt some doors'
    },

    ['gas_mask'] = {
        label = 'Gas mask',
        weight = 500,
        stack = true,
        close = true,
        description = 'Protects from lethal gas'
    },

    ['drill'] = {
        label = 'Drill',
        weight = 500,
        stack = true,
        close = true,
        description = 'Can be used to open trucks doors'
    },

    ['gold_ingot'] = {
        label = 'Gold ingot',
        weight = 500,
        stack = true,
        close = true,
        description = 'Goooold'
    },

    ['diamonds_box'] = {
        label = 'Diamond box',
        weight = 500,
        stack = true,
        close = true,
        description = 'Diamooonds'
    },

    ['lockpick'] = {
        label = 'Lockpick',
        weight = 500,
        stack = true,
        close = true,
        description = 'Used to lockpick doors'
    },

    ['painting'] = {
        label = 'Painting',
        weight = 500,
        stack = true,
        close = true,
        description = 'Expensive painting'
    },
    ```
  </Tab>
</Tabs>

Tu es prêt ! Profite bien du script 😁

## Vérification

Ouvre `/robberiescreator` en jeu. Si le menu s'ouvre, le script fonctionne correctement.

## Étape optionnelle

Une fois la base de données correctement configurée, tu peux supprimer les fichiers du dossier `robberies_creator/sql/`, pour que le script n'essaie pas de la reconfigurer à chaque démarrage.
