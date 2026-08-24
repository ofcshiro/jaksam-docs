---
title: "Modules"
description: "Remplace des fonctionnalités par défaut comme la banque, le text UI et les logs par tes propres modules personnalisés."
icon: "puzzle-piece"
---

Les modules sont un moyen simple pour Dealerships Creator de remplacer certaines fonctionnalités par défaut (banque, text UI, logs).

Pour choisir un module existant, ouvre le menu `/dealershipscreator`, va dans les paramètres, et choisis-le. Aussi simple que ça.

### Modules disponibles

| Catégorie | Options disponibles |
| --- | --- |
| Banque | `default`, `example`, `okokbanking` |
| Logs | `custom`, `jaksam` |
| Text UI | `esx`, `none`, `ox_lib` |

### Créer un module personnalisé

Choisis la catégorie pour laquelle tu veux créer un module. Chaque onglet te guide étape par étape pour cette catégorie et te donne un modèle prêt à modifier.

<Tabs>
  <Tab title="Banque">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `dealerships_creator/_modules/banking`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `example`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions nécessaires">
        Ouvre le fichier renommé et modifie-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "banking"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Retourne le solde actuel du compte de la société/entreprise indiquée
        Integrations[moduleType][moduleName].getSocietyMoney = function(societyName)
            -- Ajoute ton code ici
        end

        -- Ajoute de l'argent au compte de la société/entreprise indiquée
        Integrations[moduleType][moduleName].giveMoneyToSociety = function(societyName, amount)
            -- Ajoute ton code ici
        end

        -- Retire de l'argent du compte de la société/entreprise indiquée
        Integrations[moduleType][moduleName].removeMoneyFromSociety = function(societyName, amount)
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Logs">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `dealerships_creator/_modules/logs`.
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

  <Tab title="Text UI">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `dealerships_creator/_modules/textui`.
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
