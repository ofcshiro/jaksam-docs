---
title: "Modules"
description: "Remplace des fonctionnalités par défaut comme la barre de progression, le dispatch et les logs par tes propres modules personnalisés."
icon: "puzzle-piece"
---

Les modules sont un moyen simple pour Robberies Creator de remplacer certaines fonctionnalités par défaut (barre de progression, dispatch, logs).

Pour choisir un module existant, ouvre le menu `/robberiescreator`, va dans les paramètres, et choisis-le. C'est aussi simple que ça.

### Modules disponibles

| Catégorie | Options disponibles |
| --- | --- |
| Dispatch | `codesign`, `default`, `rcore`, `roadphone` |
| Logs | `custom`, `jaksam` |
| Barre de progression | `jaksam`, `ox_lib`, `qb-core` |
| Text UI | `esx`, `none`, `ox_lib` |

### Créer un module personnalisé

Choisis la catégorie pour laquelle tu veux créer un module. Chaque onglet te guide étape par étape pour cette catégorie et te donne un modèle prêt à modifier.

<Tabs>
  <Tab title="Dispatch">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `robberies_creator/_modules/dispatch`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `default`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions nécessaires">
        Ouvre le fichier renommé et modifie-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "dispatch"
        local moduleName = "yourModuleName" -- Renomme selon l'intégration que tu crées

        -- Ne pas toucher, nécessaire pour apparaître dans les paramètres in-game
        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- S'exécute une fois par appel, côté serveur
        Integrations[moduleType][moduleName].alertPoliceServerSide = function(coords, message, category)
            if not IsDuplicityVersion() then return end

            -- Ajoute ton code ici (par exemple, appeler l'export/event de ton script de dispatch pour alerter la police)
        end

        -- S'exécute côté client, sur le client de chaque policier
        Integrations[moduleType][moduleName].alertPoliceMemberClientSide = function(coords, message, category)
            if IsDuplicityVersion() then return end

            -- Ajoute ton code ici (par exemple, afficher un blip/notification au policier)
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Logs">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `robberies_creator/_modules/logs`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `jaksam`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions nécessaires">
        Ouvre le fichier renommé et modifie-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "logs"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Envoie une entrée de log (par exemple vers un webhook Discord ou un script de logs personnalisé)
        Integrations[moduleType][moduleName].log = function(playerId, title, description, type, logType)
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Barre de progression">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `robberies_creator/_modules/progressbar`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `jaksam`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions nécessaires">
        Ouvre le fichier renommé et modifie-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "progressbar"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Démarre une barre de progression pour la durée donnée (ms), avec le texte et la couleur donnés
        Integrations[moduleType][moduleName].start = function(time, text, hexColor)
            -- Ajoute ton code ici
        end

        -- Arrête/masque la barre de progression
        Integrations[moduleType][moduleName].stop = function()
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Text UI">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `robberies_creator/_modules/textui`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `ox_lib`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions nécessaires">
        Ouvre le fichier renommé et modifie-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "textui"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Affiche une invite de text UI avec le message donné
        Integrations[moduleType][moduleName].show = function(message)
            -- Ajoute ton code ici
        end

        -- Masque l'invite de text UI
        Integrations[moduleType][moduleName].hide = function()
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>
</Tabs>
