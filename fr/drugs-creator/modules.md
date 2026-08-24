---
title: "Modules"
description: "Remplace des fonctionnalités par défaut comme notify, la barre de progression, le stash et les logs par tes propres modules personnalisés."
icon: "puzzle-piece"
---

Les modules sont un moyen simple pour Drugs Creator de remplacer certaines fonctionnalités par défaut (notify, barre de progression, stash, logs).

Pour choisir un module existant, ouvre le menu `/drugscreator`, va dans les paramètres, et sélectionne-le. Aussi simple que ça.

### Modules disponibles

| Catégorie | Options disponibles |
| --- | --- |
| Dispatch | `codesign`, `default`, `rcore`, `roadphone` |
| Gangs | `default` |
| Inventory | `jaksam_inventory`, `ox_inventory`, `qb-inventory` |
| Logs | `custom`, `jaksam` |
| Menu | `menu_default`, `ox_context`, `ox_lib` |
| Progress Bar | `jaksam`, `ox_lib`, `qb-core` |
| Stash | `jaksam_inventory`, `ox-inventory`, `qb-inventory` |
| Text UI | `esx`, `none`, `ox_lib` |

### Créer un module personnalisé

Choisis la catégorie pour laquelle tu veux créer un module. Chaque onglet te guide pas à pas pour cette catégorie et te fournit un modèle prêt à être modifié.

<Tabs>
  <Tab title="Dispatch">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `drugs_creator/_modules/dispatch`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `default`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé et modifie-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "dispatch"
        local moduleName = "yourModuleName" -- Renomme pour correspondre à l'intégration que tu crées

        -- Ne touche pas à ça, nécessaire pour apparaître dans les paramètres ingame
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

            -- Ajoute ton code ici (par exemple, afficher un blip/une notification au policier)
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Gangs">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `drugs_creator/_modules/gangs`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `default`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé et modifie-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "gangs"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        --- Vérifie si un joueur a la permission de gang selon sa gang et son niveau de grade, CÔTÉ SERVEUR
        --- @param playerId number - L'ID serveur du joueur
        --- @param allowedGangs table<string, boolean|table<string, boolean>> - Table des gangs autorisées et de leurs grades
        --- @return boolean|nil - Si le joueur a la permission
        Integrations[moduleType][moduleName].isPlayerGangAllowed = function(playerId, allowedGangs)
            -- Ajoute ton code ici
        end

        --- Même vérification, mais CÔTÉ CLIENT
        --- @param allowedGangs table<string, boolean|table<string, boolean>>
        --- @return boolean|nil
        Integrations[moduleType][moduleName].isClientGangAllowed = function(allowedGangs)
            -- Ajoute ton code ici
        end

        --- Retourne le nom de la gang d'un joueur, CÔTÉ SERVEUR
        --- @param playerId number
        --- @return string|nil
        Integrations[moduleType][moduleName].getPlayerGangName = function(playerId)
            -- Ajoute ton code ici
        end

        --- Retourne le nom de la gang du joueur local, CÔTÉ CLIENT
        --- @return string|nil
        Integrations[moduleType][moduleName].getClientGangName = function()
            -- Ajoute ton code ici
        end

        --- Retourne toutes les gangs disponibles dans le jeu
        --- @return table<string, { label: string, grades: table<number, { grade: number, label: string }> }>
        Integrations[moduleType][moduleName].getAllGangs = function()
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Inventory">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `drugs_creator/_modules/inventory`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `jaksam_inventory`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé et modifie-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "inventory"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Retourne l'ID du slot qui contient l'item donné, ou nil si aucun
        Integrations[moduleType][moduleName].getSlotIdWithItem = function(playerId, itemName, metadata)
            -- Ajoute ton code ici
        end

        -- Définit des metadata sur l'item du slot donné
        Integrations[moduleType][moduleName].setItemMetadata = function(playerId, slotId, metadata)
            -- Ajoute ton code ici
        end

        -- Retourne les données de l'item stocké dans le slot donné
        Integrations[moduleType][moduleName].getSlotItem = function(playerId, slotId)
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Logs">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `drugs_creator/_modules/logs`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `jaksam`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé et modifie-le pour qu'il corresponde aux events du script tiers que tu intègres :

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

  <Tab title="Menu">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `drugs_creator/_modules/menu`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `menu_default`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé et modifie-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "menu"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Ouvre un menu avec les éléments donnés
        Integrations[moduleType][moduleName].open = function(id, title, elements, onSelect, onClose)
            -- Ajoute ton code ici
        end

        -- Ferme tout menu ouvert par ce module
        Integrations[moduleType][moduleName].closeAll = function()
            -- Ajoute ton code ici
        end

        -- Demande au joueur un nombre entre min et max
        Integrations[moduleType][moduleName].askQuantity = function(title, min, max)
            -- Ajoute ton code ici
        end

        -- Demande au joueur une saisie de texte libre
        Integrations[moduleType][moduleName].askInput = function(title)
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Progress Bar">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `drugs_creator/_modules/progressbar`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `jaksam`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
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

  <Tab title="Stash">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `drugs_creator/_modules/stash`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `jaksam_inventory`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé (côté client et serveur) et modifie-le pour qu'il corresponde aux events du script tiers que tu intègres :

        Client :
        ```lua
        local moduleType = "stash"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Ouvre l'UI du stash pour le joueur
        Integrations[moduleType][moduleName].open = function(stashId)
            -- Ajoute ton code ici
        end
        ```
        Serveur :
        ```lua
        -- Enregistre le stash pour qu'il existe et puisse être ouvert
        Integrations[moduleType][moduleName].register = function(options)
            -- Ajoute ton code ici
        end

        -- Ajoute un item au stash
        Integrations[moduleType][moduleName].addItem = function(stashId, itemName, amount, metadata)
            -- Ajoute ton code ici
        end

        -- Retire un item du stash
        Integrations[moduleType][moduleName].removeItem = function(stashId, itemName, amount, metadata)
            -- Ajoute ton code ici
        end

        -- Retourne combien de itemName se trouvent actuellement dans le stash
        Integrations[moduleType][moduleName].getItemCount = function(stashId, itemName)
            -- Ajoute ton code ici
        end

        -- Retourne si amount de itemName supplémentaires tiendraient encore dans le stash
        Integrations[moduleType][moduleName].canAddItem = function(stashId, itemName, amount)
            -- Ajoute ton code ici
        end

        -- Retire tous les items du stash
        Integrations[moduleType][moduleName].clearStash = function(stashId)
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>

  <Tab title="Text UI">
    <Steps>
      <Step title="Va dans le dossier des modules">
        Va dans le dossier `drugs_creator/_modules/textui`.
      </Step>
      <Step title="Duplique un module existant">
        Copie un module existant (par exemple `ox_lib`) et colle-le dans le même dossier comme modèle.
      </Step>
      <Step title="Renomme la copie">
        Renomme la copie collée pour qu'elle corresponde à l'intégration que tu veux créer.
      </Step>
      <Step title="Implémente les fonctions requises">
        Ouvre le fichier renommé et modifie-le pour qu'il corresponde aux events du script tiers que tu intègres :

        ```lua
        local moduleType = "textui"
        local moduleName = "yourModuleName"

        Integrations.modules = Integrations.modules or {}
        Integrations.modules[moduleType] = Integrations.modules[moduleType] or {}
        Integrations[moduleType] = Integrations[moduleType] or {}
        Integrations[moduleType][moduleName] = {}
        table.insert(Integrations.modules[moduleType], moduleName)

        -- Affiche un message d'UI textuelle avec le message donné
        Integrations[moduleType][moduleName].show = function(message)
            -- Ajoute ton code ici
        end

        -- Masque le message d'UI textuelle
        Integrations[moduleType][moduleName].hide = function()
            -- Ajoute ton code ici
        end
        ```
      </Step>
    </Steps>
  </Tab>
</Tabs>
