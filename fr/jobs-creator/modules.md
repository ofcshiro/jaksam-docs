---
title: "Modules"
description: "Remplace les fonctionnalités par défaut comme notify, progress bar, stash et logs par tes propres modules personnalisés."
icon: "puzzle-piece"
---

Les modules sont un moyen simple pour Jobs Creator de remplacer certaines fonctionnalités par défaut (notify, progress bar, stash, logs).

Pour choisir un module existant, ouvre le menu `/jobscreator`, va dans les paramètres, et sélectionne-le. Aussi simple que ça.

### Modules Disponibles

| Catégorie | Options Disponibles |
| --- | --- |
| Banking | `default`, `example`, `okok` |
| Boss | `default`, `example` |
| Logs | `custom`, `jaksam` |
| Notify | `default`, `example`, `origen`, `ox_lib` |
| Outfits | `default`, `illenium-appearance`, `rcore_clothing` |
| Progress Bar | `jaksam`, `ox_lib`, `qb-core` |
| Search Player | `jaksam`, `jaksam_inventory`, `ox_inventory` |
| Skillcheck | `jaksam`, `ox_lib` |
| Stash | `default`, `hc_inventory`, `jaksam_inventory`, `ox-inventory`, `qb-inventory` |
| Text UI | `esx`, `jg-text`, `none`, `ox_lib` |

### Créer un Module Personnalisé

Choisis la catégorie pour laquelle tu veux créer un module. Chaque onglet te guide pas à pas selon les étapes exactes pour cette catégorie et te donne un modèle prêt à éditer.

<Tabs>
  <Tab title="Banking">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `jobs_creator/_modules/banking`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `example`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé et édite-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "banking"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Retourne le solde actuel du compte de la société/entreprise donnée
        Integrations[moduleType][moduleName].getSocietyMoney = function(societyName)
            -- Ajoute ton code ici
        end

        -- Ajoute de l'argent au compte de la société/entreprise donnée
        Integrations[moduleType][moduleName].giveMoneyToSociety = function(societyName, amount)
            -- Ajoute ton code ici
        end

        -- Retire de l'argent du compte de la société/entreprise donnée
        Integrations[moduleType][moduleName].removeMoneyFromSociety = function(societyName, amount)
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Boss">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `jobs_creator/_modules/boss`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `example`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé et édite-le pour qu'il corresponde aux events du script tiers que tu intègres. Les quatre fonctions sont des overrides optionnels : retourner `nil` laisse intact le comportement par défaut de Jobs Creator.

        ```lua
        local moduleType = "boss"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Appelée avant de retourner la liste des employés au client, retourne la liste (éventuellement modifiée)
        Integrations[moduleType][moduleName].modifyEmployeesList = function(employeesArray, jobName)
            -- Ajoute ton code ici

            return employeesArray
        end

        -- Appelée quand un employé est licencié. Retourne true si tu l'as géré toi-même, nil pour garder le comportement par défaut
        Integrations[moduleType][moduleName].fireEmployee = function(playerId, employeeIdentifier, jobName)
            -- Ajoute ton code ici

            return nil
        end

        -- Appelée avant de recruter un joueur. Retourne true si tu l'as géré toi-même, nil pour garder le comportement par défaut
        Integrations[moduleType][moduleName].recruitPlayer = function(playerId, targetId, jobName)
            -- Ajoute ton code ici

            return nil
        end

        -- Appelée avant de changer le grade d'un employé. Retourne true si tu l'as géré toi-même, nil pour garder le comportement par défaut
        Integrations[moduleType][moduleName].changeGradeToEmployee = function(playerId, employeeIdentifier, newGrade, jobName)
            -- Ajoute ton code ici

            return nil
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Logs">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `jobs_creator/_modules/logs`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `jaksam`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé et édite-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "logs"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Envoie une entrée de log (par exemple, vers un webhook Discord ou un script de logs personnalisé)
        Integrations[moduleType][moduleName].log = function(playerId, title, description, type, logType)
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Notify">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `jobs_creator/_modules/notify`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `example`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé et édite-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "notify"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Affiche une notification avec un message brut et une version (éventuellement) colorée de celui-ci
        Integrations[moduleType][moduleName].showNotification = function(message, coloredMessage)
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Outfits">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `jobs_creator/_modules/outfits`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `rcore_clothing`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé et édite-le pour qu'il corresponde aux events du script tiers que tu intègres. `openExternalMenu` contrôle les autres : retourne `true` pour remplacer entièrement l'UI des tenues par ton propre script (seules `openWardrobe`/`openJobOutfits` sont utilisées), ou `false` pour continuer à utiliser le menu de Jobs Creator (`getPlayerClothes`/`setPlayerClothes` sont utilisées à la place).

        ```lua
        local moduleType = "outfits"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Retourne true pour remplacer entièrement l'UI des tenues par ton propre script, false pour continuer à utiliser le menu de Jobs Creator
        Integrations[moduleType][moduleName].openExternalMenu = function()
            return false
        end

        -- Ouvre le menu des tenues sauvegardées du joueur de ton script (utilisé seulement si openExternalMenu retourne true)
        Integrations[moduleType][moduleName].openWardrobe = function()
            -- Ajoute ton code ici
        end

        -- Ouvre le menu des tenues de job sauvegardées de ton script, remplaçant entièrement la fonctionnalité de tenues de job de Jobs Creator (utilisé seulement si openExternalMenu retourne true)
        Integrations[moduleType][moduleName].openJobOutfits = function()
            -- Ajoute ton code ici
        end

        -- Retourne la table de la tenue/vêtements actuelle du joueur (utilisé seulement si openExternalMenu retourne false)
        Integrations[moduleType][moduleName].getPlayerClothes = function()
            -- Ajoute ton code ici
        end

        -- Applique la table de tenue/vêtements donnée au joueur (utilisé seulement si openExternalMenu retourne false)
        Integrations[moduleType][moduleName].setPlayerClothes = function(outfit, saveAfterRestart)
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Progress Bar">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `jobs_creator/_modules/progressbar`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `jaksam`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé et édite-le pour qu'il corresponde aux events du script tiers que tu intègres :

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
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Search Player">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `jobs_creator/_modules/search_player`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `ox_inventory`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé et édite-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "search_player"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Ouvre l'UI de fouille/inventaire du joueur ciblé (par exemple, après avoir vérifié qu'il est menotté)
        Integrations[moduleType][moduleName].search = function(targetServerId)
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Skillcheck">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `jobs_creator/_modules/skillcheck`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `ox_lib`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé et édite-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "skillcheck"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Démarre un minijeu de skillcheck avec la difficulté et la vitesse données
        Integrations[moduleType][moduleName].start = function(difficulty, speed)
            -- Ajoute ton code ici
        end

        -- Annule le minijeu de skillcheck en cours
        Integrations[moduleType][moduleName].cancel = function()
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Stash">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `jobs_creator/_modules/stash`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `jaksam_inventory`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé et édite-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "stash"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Ouvre l'UI du stash pour le marqueur donné
        Integrations[moduleType][moduleName].open = function(type, markerId)
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Text UI">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `jobs_creator/_modules/textui`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `ox_lib`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé et édite-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "textui"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Affiche un prompt de text UI avec le message donné
        Integrations[moduleType][moduleName].show = function(message)
            -- Ajoute ton code ici
        end

        -- Cache le prompt de text UI
        Integrations[moduleType][moduleName].hide = function()
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>
</Tabs>
