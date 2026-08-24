---
title: "Installation"
description: "Installe Jobs Creator sur ton serveur FiveM avec ESX ou QBCore. Suis le guide de configuration spécifique au framework et configure la base de données et les items requis."
icon: "download"
---

Mets **Jobs Creator** en marche sur ton serveur FiveM en seulement quelques étapes.

## Prérequis

- **ESX** ou **QBCore**
- Sur QBCore, le script [`menu_default`](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing) (voir l'étape 4 ci-dessous)

Choisis ton framework ci-dessous pour voir les instructions d'installation correspondantes.

<Tabs>
  <Tab title="ESX" icon="server">
    <Steps>
      <Step title="Télécharge Jobs Creator">
        Télécharge **Jobs Creator** et extrais-le dans le dossier `resources` de ton serveur.
      </Step>
      <Step title="Configure server.cfg">
        Ajoute ce qui suit à ton `server.cfg` :

        ```cfg
        add_unsafe_worker_permission jobs_creator # Permet à jobs_creator de s'installer automatiquement
        ensure jobs_creator
        ```
      </Step>
      <Step title="Configure la base de données">
        Jobs Creator **configurera automatiquement la base de données** au démarrage de la resource.

        Si la configuration automatique échoue, tu peux exécuter manuellement les fichiers SQL situés dans :

        ```text
        jobs_creator/sql/
        ```
      </Step>
      <Step title="Ajoute les items inclus">
        <Note>
          Ajouter les items inclus est **optionnel**. Choisis le fichier SQL qui correspond à ton système d'inventaire ESX.
        </Note>

        **Inventaire basé sur le poids**

        Exécute :

        ```text
        jobs_creator/sql/items_weight.sql
        ```

        **Inventaire basé sur la limite**

        Exécute :

        ```text
        jobs_creator/sql/items_limit.sql
        ```
      </Step>
    </Steps>
  </Tab>
  <Tab title="QBCore" icon="server">
    <Steps>
      <Step title="Télécharge Jobs Creator">
        Télécharge **Jobs Creator** et extrais-le dans le dossier `resources` de ton serveur.
      </Step>
      <Step title="Configure server.cfg">
        Ajoute ce qui suit à ton `server.cfg` :

        ```cfg
        add_unsafe_worker_permission jobs_creator # Permet à jobs_creator de s'installer automatiquement
        ensure jobs_creator
        ```
      </Step>
      <Step title="Configure la base de données">
        Jobs Creator **configurera automatiquement la base de données** au démarrage de la resource.

        Si la configuration automatique échoue, tu peux exécuter manuellement les fichiers SQL situés dans :

        ```text
        jobs_creator/sql/
        ```
      </Step>
      <Step title="Installe menu_default">
        Télécharge [`menu_default`](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing) et extrais-le dans le dossier `resources` de ton serveur.

        Puis ajoute `menu_default` à ton `server.cfg` :

        ```cfg
        ensure menu_default
        ```
      </Step>
      <Step title="Ajoute les items inclus">
        <Note>
          Ajouter les items inclus est **optionnel**.
        </Note>

        Ouvre :

        ```text
        qb-core/shared/items.lua
        ```

        Ajoute les items suivants au bas de la table d'items :

        ```lua
        ['fixkit'] = {
            ['name'] = 'fixkit',
            ['label'] = 'Fixkit',
            ['weight'] = 500,
            ['type'] = 'item',
            ['image'] = 'your_image.png',
            ['unique'] = false,
            ['useable'] = false,
            ['shouldClose'] = false,
            ['combinable'] = nil
        },
        
        ['medikit'] = {
            ['name'] = 'medikit',
            ['label'] = 'Medikit',
            ['weight'] = 500,
            ['type'] = 'item',
            ['image'] = 'your_image.png',
            ['unique'] = false,
            ['useable'] = false,
            ['shouldClose'] = false,
            ['combinable'] = nil
        },
        
        ['sponge'] = {
            ['name'] = 'sponge',
            ['label'] = 'Sponge',
            ['weight'] = 500,
            ['type'] = 'item',
            ['image'] = 'your_image.png',
            ['unique'] = false,
            ['useable'] = false,
            ['shouldClose'] = false,
            ['combinable'] = nil
        },
        
        ['handcuffs'] = {
            ['name'] = 'handcuffs',
            ['label'] = 'Handcuffs',
            ['weight'] = 500,
            ['type'] = 'item',
            ['image'] = 'your_image.png',
            ['unique'] = false,
            ['useable'] = false,
            ['shouldClose'] = false,
            ['combinable'] = nil
        },
        
        ['lockpick'] = {
            ['name'] = 'lockpick',
            ['label'] = 'Lockpick',
            ['weight'] = 500,
            ['type'] = 'item',
            ['image'] = 'your_image.png',
            ['unique'] = false,
            ['useable'] = false,
            ['shouldClose'] = false,
            ['combinable'] = nil
        },
        
        ['bandage'] = {
            ['name'] = 'bandage',
            ['label'] = 'Bandage',
            ['weight'] = 500,
            ['type'] = 'item',
            ['image'] = 'your_image.png',
            ['unique'] = false,
            ['useable'] = false,
            ['shouldClose'] = false,
            ['combinable'] = nil
        },
        ```
      </Step>
    </Steps>
  </Tab>
</Tabs>

## Vérification

Ouvre `/jobscreator` en jeu. Si le menu s'ouvre, le script fonctionne correctement.

## Nettoyer les Fichiers SQL

<Note>
  Une fois que la base de données a été configurée avec succès, tu peux optionnellement supprimer les fichiers SQL de `jobs_creator/sql/`.
</Note>

Les fichiers SQL ne sont nécessaires que pour la configuration manuelle de la base de données ou lors de l'ajout des items ESX inclus.
