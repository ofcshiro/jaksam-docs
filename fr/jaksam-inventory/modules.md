---
title: "Modules"
description: "Remplace des fonctionnalités par défaut comme les gangs, la barre de progression, le text UI et les logs par tes propres modules personnalisés."
icon: "puzzle-piece"
---

Les modules sont un moyen simple pour Jaksam Inventory de remplacer certaines fonctionnalités par défaut (gangs, barre de progression, text UI, logs).

Pour choisir un module existant, ouvre le menu admin `/inventory`, va dans les paramètres, et choisis-le. Aussi simple que ça.

### Modules disponibles

| Catégorie | Options disponibles |
| --- | --- |
| Gangs | `default` |
| Logs | `custom`, `jaksam` |
| Barre de progression | `jaksam`, `ox_lib`, `qb-core` |
| Text UI | `esx`, `none`, `ox_lib` |

### Créer un module personnalisé

Choisis la catégorie pour laquelle tu veux créer un module. Chaque onglet te guide étape par étape pour cette catégorie et te donne un modèle prêt à modifier.

<Tabs>
  <Tab title="Gangs">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `jaksam_inventory/_modules/gangs`.
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
        local moduleType = "gangs"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Vérifie si un joueur a la permission de gang selon son gang et son niveau de grade, CÔTÉ SERVEUR
        -- Format allowedGangs : { gangName = true } (tous les grades autorisés) ou { gangName = { ["0"] = true, ["1"] = true } } (grades spécifiques)
        Integrations[moduleType][moduleName].isPlayerGangAllowed = function(playerId, allowedGangs)
            -- Ajoute ton code ici
        end

        -- Même vérification, mais CÔTÉ CLIENT
        Integrations[moduleType][moduleName].isClientGangAllowed = function(allowedGangs)
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

  <Tab title="Logs">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `jaksam_inventory/_modules/logs`.
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
        Va dans le dossier `jaksam_inventory/_modules/progressbar`.
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
        Va dans le dossier `jaksam_inventory/_modules/textui`.
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
