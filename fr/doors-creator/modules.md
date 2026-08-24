---
title: "Modules"
description: "Remplace des fonctionnalités par défaut comme le crochetage, le dispatch et les logs par tes propres modules personnalisés."
icon: "puzzle-piece"
---

Les modules sont un moyen simple pour Doors Creator de remplacer certaines fonctionnalités par défaut (crochetage, dispatch, logs).

Pour choisir un module existant, ouvre le menu `/doorscreator`, va dans les paramètres, et choisis-le. C'est tout.

### Modules disponibles

| Catégorie | Options disponibles |
| --- | --- |
| Dispatch | `codesign`, `default`, `rcore`, `roadphone` |
| Gangs | `default` |
| Crochetage | `default`, `ox_lib` |
| Logs | `custom`, `jaksam` |
| Barre de progression | `jaksam`, `ox_lib`, `qb-core` |
| Text UI | `esx`, `none`, `ox_lib` |

### Créer un module personnalisé

Choisis la catégorie pour laquelle tu veux créer un module. Chaque onglet te guide à travers les étapes exactes pour cette catégorie et te fournit un modèle prêt à être modifié.

<Tabs>
  <Tab title="Dispatch">
    <Steps>
      <Step title="Aller dans le dossier des modules">
        Va dans le dossier `doors_creator/_modules/dispatch`.
      </Step>
      <Step title="Dupliquer un module existant">
        Copie un module existant (ex : `default`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renommer la copie">
        Renomme la copie collée pour correspondre à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémenter les fonctions requises">
        Ouvre le fichier renommé et modifie-le pour correspondre aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "dispatch"
        local moduleName = "yourModuleName" -- Renomme pour correspondre à l'intégration que tu crées

        -- Ne pas toucher, requis pour apparaître dans les paramètres in-game
        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- S'exécute une fois par appel, côté serveur
        Integrations[moduleType][moduleName].alertPoliceServerSide = function(coords, message, category)
            if not IsDuplicityVersion() then return end

            -- Ajoute ton code ici (ex : appeler l'export/event de ton script de dispatch pour alerter la police)
        end

        -- S'exécute côté client, sur le client de chaque policier
        Integrations[moduleType][moduleName].alertPoliceMemberClientSide = function(coords, message, category)
            if IsDuplicityVersion() then return end

            -- Ajoute ton code ici (ex : afficher un blip/une notification à l'officier)
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Gangs">
    <Steps>
      <Step title="Aller dans le dossier des modules">
        Va dans le dossier `doors_creator/_modules/gangs`.
      </Step>
      <Step title="Dupliquer un module existant">
        Copie un module existant (ex : `default`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renommer la copie">
        Renomme la copie collée pour correspondre à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémenter les fonctions requises">
        Ouvre le fichier renommé et modifie-le pour correspondre aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "gangs"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Vérifie si un joueur a la permission d'ouvrir une porte selon son gang et son grade, CÔTÉ SERVEUR
        -- Format allowedGangs : { gangName = true } (tous les grades autorisés) ou { gangName = { ["0"] = true, ["1"] = true } } (grades spécifiques)
        Integrations[moduleType][moduleName].isPlayerGangAllowedToOpenDoor = function(playerId, allowedGangs)
            -- Ajoute ton code ici
        end

        -- Retourne tous les gangs disponibles dans le jeu (voir un module existant pour le format exact de la table)
        Integrations[moduleType][moduleName].getAllGangs = function()
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Crochetage">
    <Steps>
      <Step title="Aller dans le dossier des modules">
        Va dans le dossier `doors_creator/_modules/lockpick`.
      </Step>
      <Step title="Dupliquer un module existant">
        Copie un module existant (ex : `default`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renommer la copie">
        Renomme la copie collée pour correspondre à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémenter les fonctions requises">
        Ouvre le fichier renommé et modifie-le pour correspondre aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "lockpick"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Démarre le minijeu de crochetage avec le nombre de tentatives donné, et retourne s'il a réussi
        Integrations[moduleType][moduleName].startLockpick = function(attempts)
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Logs">
    <Steps>
      <Step title="Aller dans le dossier des modules">
        Va dans le dossier `doors_creator/_modules/logs`.
      </Step>
      <Step title="Dupliquer un module existant">
        Copie un module existant (ex : `jaksam`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renommer la copie">
        Renomme la copie collée pour correspondre à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémenter les fonctions requises">
        Ouvre le fichier renommé et modifie-le pour correspondre aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "logs"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Envoie une entrée de log (ex : vers un webhook Discord ou un script de logs personnalisé)
        Integrations[moduleType][moduleName].log = function(playerId, title, description, type, logType)
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Barre de progression">
    <Steps>
      <Step title="Aller dans le dossier des modules">
        Va dans le dossier `doors_creator/_modules/progressbar`.
      </Step>
      <Step title="Dupliquer un module existant">
        Copie un module existant (ex : `jaksam`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renommer la copie">
        Renomme la copie collée pour correspondre à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémenter les fonctions requises">
        Ouvre le fichier renommé et modifie-le pour correspondre aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "progressbar"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Démarre une barre de progression pour le temps donné (ms), avec le texte et la couleur donnés
        Integrations[moduleType][moduleName].start = function(time, text, hexColor)
            -- Ajoute ton code ici
        end

        -- Arrête/cache la barre de progression
        Integrations[moduleType][moduleName].stop = function()
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Text UI">
    <Steps>
      <Step title="Aller dans le dossier des modules">
        Va dans le dossier `doors_creator/_modules/textui`.
      </Step>
      <Step title="Dupliquer un module existant">
        Copie un module existant (ex : `ox_lib`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renommer la copie">
        Renomme la copie collée pour correspondre à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémenter les fonctions requises">
        Ouvre le fichier renommé et modifie-le pour correspondre aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "textui"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Affiche un message text UI avec le message donné
        Integrations[moduleType][moduleName].show = function(message)
            -- Ajoute ton code ici
        end

        -- Cache le message text UI
        Integrations[moduleType][moduleName].hide = function()
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>
</Tabs>
