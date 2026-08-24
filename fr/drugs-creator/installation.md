---
title: "Installation"
description: "Installe Drugs Creator sur ton serveur FiveM avec ESX, QBCore ou OX Inventory, avec la configuration optionnelle des items par défaut."
icon: "download"
---

L'installation du script est extrêmement simple.

## Prérequis

- **ESX**, **QBCore** ou **OX Inventory**

<Danger>
  N'utilise **PAS** FileZilla pour envoyer les fichiers, sinon le script **NE** fonctionnera **PAS**.

  Utilise [WinSCP](https://winscp.net/eng/download.php) à la place.
</Danger>

<Tabs>
  <Tab title="ESX">
    <Steps>
      <Step title="Télécharge et extrais">
        Télécharge le script et extrais-le dans tes resources.
      </Step>
      <Step title="Ajoute-le au démarrage automatique">
        Ajoute le script à ton démarrage automatique (exemple : `server.cfg`).
      </Step>
      <Step title="Configuration de la base de données">
        Le script configurera **automatiquement** la base de données. Si ce n'est pas le cas, tu peux exécuter manuellement les fichiers du dossier `drugs_creator/sql/`.
      </Step>
    </Steps>

    ### Ajouter les items — Optionnel

    Si tu veux utiliser les items/drogues par défaut, suis les étapes ci-dessous.

    Pour ajouter les items/drogues préconçus, il te suffit d'exécuter le fichier `drugs_creator/sql/items_limit.sql` **ou** `drugs_creator/sql/items_weight.sql`, selon que ton serveur utilise le système limit ou weight.

    <Info>
      La dernière version d'ESX utilise **weight**.
    </Info>

    <Danger>
      Si ça ne fonctionne pas, assure-toi d'utiliser la dernière version officielle d'ESX avec les dépendances requises.
    </Danger>
  </Tab>
  <Tab title="QBCore">
    <Steps>
      <Step title="Télécharge et extrais">
        Télécharge le script et extrais-le dans tes resources.
      </Step>
      <Step title="Ajoute-le au démarrage automatique">
        Ajoute le script à ton démarrage automatique (exemple : `server.cfg`).
      </Step>
      <Step title="Configuration de la base de données">
        Le script configurera **automatiquement** la base de données. Si ce n'est pas le cas, tu peux exécuter manuellement les fichiers du dossier `drugs_creator/sql/`.
      </Step>
      <Step title="Installe menu_default">
        Télécharge et extrais le script [menu_default](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing) dans tes resources, **sans le renommer**, et ajoute-le à ton démarrage automatique (exemple : `server.cfg`).
      </Step>
    </Steps>

    ### Ajouter les items — Optionnel

    Pour ajouter les nouveaux items, édite le fichier `qb-core/shared/items.lua` et ajoute le code suivant en bas de la table :

    ```lua
    ['ammonium_nitrate'] = {['name'] = 'ammonium_nitrate', ['label'] = 'Ammonium nitrate', ['weight'] = 500, ['type'] = 'item', ['image'] = 'ammonium_nitrate.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['carbon'] = {['name'] = 'carbon', ['label'] = 'Carbon', ['weight'] = 500, ['type'] = 'item', ['image'] = 'carbon.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['codeine'] = {['name'] = 'codeine', ['label'] = 'Codeine', ['weight'] = 500, ['type'] = 'item', ['image'] = 'codeine.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['drink_sprite'] = {['name'] = 'drink_sprite', ['label'] = 'Sprite', ['weight'] = 500, ['type'] = 'item', ['image'] = 'drink_sprite.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['drug_ecstasy'] = {['name'] = 'drug_ecstasy', ['label'] = 'Ecstasy', ['weight'] = 500, ['type'] = 'item', ['image'] = 'drug_ecstasy.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['drug_lean'] = {['name'] = 'drug_lean', ['label'] = 'Lean', ['weight'] = 500, ['type'] = 'item', ['image'] = 'drug_lean.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['drug_lsd'] = {['name'] = 'drug_lsd', ['label'] = 'LSD', ['weight'] = 500, ['type'] = 'item', ['image'] = 'drug_lsd.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['drug_meth'] = {['name'] = 'drug_meth', ['label'] = 'Meth', ['weight'] = 500, ['type'] = 'item', ['image'] = 'drug_meth.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['hydrogen'] = {['name'] = 'hydrogen', ['label'] = 'Hydrogen', ['weight'] = 500, ['type'] = 'item', ['image'] = 'hydrogen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['ice'] = {['name'] = 'ice', ['label'] = 'Ice', ['weight'] = 500, ['type'] = 'item', ['image'] = 'ice.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['jolly_ranchers'] = {['name'] = 'jolly_ranchers', ['label'] = 'Jolly Ranchers', ['weight'] = 500, ['type'] = 'item', ['image'] = 'jolly_ranchers.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['liquid_sulfur'] = {['name'] = 'liquid_sulfur', ['label'] = 'Liquid Sulfur', ['weight'] = 500, ['type'] = 'item', ['image'] = 'liquid_sulfur.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['muriatic_acid'] = {['name'] = 'muriatic_acid', ['label'] = 'Muriatic Acid', ['weight'] = 500, ['type'] = 'item', ['image'] = 'muriatic_acid.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['nitrogen'] = {['name'] = 'nitrogen', ['label'] = 'Nitrogen', ['weight'] = 500, ['type'] = 'item', ['image'] = 'nitrogen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['oxygen'] = {['name'] = 'oxygen', ['label'] = 'Oxygen', ['weight'] = 500, ['type'] = 'item', ['image'] = 'oxygen.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['pseudoefedrine'] = {['name'] = 'pseudoefedrine', ['label'] = 'Pseudoefedrine', ['weight'] = 500, ['type'] = 'item', ['image'] = 'pseudoefedrine.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['red_sulfur'] = {['name'] = 'red_sulfur', ['label'] = 'Red Sulfur', ['weight'] = 500, ['type'] = 'item', ['image'] = 'red_sulfur.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['sodium_hydroxide'] = {['name'] = 'sodium_hydroxide', ['label'] = 'Sodium hydroxide', ['weight'] = 500, ['type'] = 'item', ['image'] = 'sodium_hydroxide.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['water'] = {['name'] = 'water', ['label'] = 'Water', ['weight'] = 500, ['type'] = 'item', ['image'] = 'water.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['cannabis'] = {['name'] = 'cannabis', ['label'] = 'Cannabis', ['weight'] = 500, ['type'] = 'item', ['image'] = 'cannabis.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['green_gelato_cannabis'] = {['name'] = 'green_gelato_cannabis', ['label'] = 'Green Gelato Cannabis', ['weight'] = 500, ['type'] = 'item', ['image'] = 'green_gelato_cannabis.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['opium'] = {['name'] = 'opium', ['label'] = 'Opium', ['weight'] = 500, ['type'] = 'item', ['image'] = 'opium.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['cocaine'] = {['name'] = 'cocaine', ['label'] = 'Cocaine', ['weight'] = 500, ['type'] = 'item', ['image'] = 'cocaine.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['meth_raw'] = {['name'] = 'meth_raw', ['label'] = 'Raw Meth', ['weight'] = 500, ['type'] = 'item', ['image'] = 'meth_raw.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['meth_processed'] = {['name'] = 'meth_processed', ['label'] = 'Processed Meth', ['weight'] = 500, ['type'] = 'item', ['image'] = 'meth_processed.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['meth'] = {['name'] = 'meth', ['label'] = 'Meth', ['weight'] = 500, ['type'] = 'item', ['image'] = 'meth.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['cocaine_raw'] = {['name'] = 'cocaine_raw', ['label'] = 'Raw Cocaine', ['weight'] = 500, ['type'] = 'item', ['image'] = 'cocaine_raw.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['cocaine_packaged'] = {['name'] = 'cocaine_packaged', ['label'] = 'Packaged Cocaine', ['weight'] = 500, ['type'] = 'item', ['image'] = 'cocaine_packaged.png', ['unique'] = false, ['useable'] = true, ['shouldClose'] = false, ['combinable'] = nil},
    ['trap_phone'] = {['name'] = 'trap_phone', ['label'] = 'Trap Phone', ['weight'] = 500, ['type'] = 'item', ['image'] = 'trap_phone.png', ['unique'] = true, ['useable'] = true, ['shouldClose'] = true, ['combinable'] = nil},
    ```

    **Exemple de capture d'écran**

    <Frame>
      ![QBCore Drugs Creator items example](/images/qb_core_drugs_creator_items.jpg)
    </Frame>
  </Tab>
  <Tab title="OX Inventory">
    Voici une liste d'items à utiliser avec OX Inventory. Tu peux même l'utiliser avec l'inventaire de jaksam, dans le paramètre "import from code".

    ```lua
    ['ammonium_nitrate'] = {
        label = 'Ammonium nitrate',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['carbon'] = {
        label = 'Carbon',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['codeine'] = {
        label = 'Codeine',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['drink_sprite'] = {
        label = 'Sprite',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['drug_ecstasy'] = {
        label = 'Ecstasy',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['drug_lean'] = {
        label = 'Lean',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['drug_lsd'] = {
        label = 'LSD',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['drug_meth'] = {
        label = 'Meth',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['hydrogen'] = {
        label = 'Hydrogen',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['ice'] = {
        label = 'Ice',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['jolly_ranchers'] = {
        label = 'Jolly Ranchers',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['liquid_sulfur'] = {
        label = 'Liquid Sulfur',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['muriatic_acid'] = {
        label = 'Muriatic Acid',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['nitrogen'] = {
        label = 'Nitrogen',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['oxygen'] = {
        label = 'Oxygen',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['pseudoefedrine'] = {
        label = 'Pseudoefedrine',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['red_sulfur'] = {
        label = 'Red Sulfur',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['sodium_hydroxide'] = {
        label = 'Sodium hydroxide',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['water'] = {
        label = 'Water',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['cannabis'] = {
        label = 'Cannabis',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['green_gelato_cannabis'] = {
        label = 'Green Gelato Cannabis',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['opium'] = {
        label = 'Opium',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['cocaine'] = {
        label = 'Cocaine',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['meth_raw'] = {
        label = 'Raw Meth',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['meth_processed'] = {
        label = 'Processed Meth',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['meth'] = {
        label = 'Meth',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['cocaine_raw'] = {
        label = 'Raw Cocaine',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['cocaine_packaged'] = {
        label = 'Packaged Cocaine',
        weight = 500,
        stack = true,
        close = false,
    },
    
    ['trap_phone'] = {
        label = 'Trap Phone',
        weight = 500,
        stack = false,
        close = true,
    },
    ```
  </Tab>
</Tabs>

Tu es prêt à démarrer ! Profite bien du script 😁

## Vérification

Ouvre `/drugscreator` ingame. Si le menu s'ouvre, le script fonctionne correctement.

## Étape optionnelle

Une fois la base de données correctement configurée, tu peux supprimer les fichiers du dossier `drugs_creator/sql/`, afin que le script n'essaie plus de configurer la base de données à chaque démarrage.
