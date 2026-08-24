---
title: "Installation"
icon: "table-rows-add-below"
description: "L'installation du script est extrêmement simple."
---

## Prérequis

- **ESX** (1.10.7, 1.11.3\+, ou 1.14.0\+), **QBCore**, ou **QBX**
- `jaksam_core`
- `oxmysql` et `ox_lib` (voir l'exemple d'ordre de démarrage pour ton framework ci-dessous)

<Warning>
  **N'utilise PAS FileZilla** pour uploader les fichiers, sinon le script ne fonctionnera **PAS**. Utilise [WinSCP](https://winscp.net/eng/download.php) à la place.
</Warning>

<Tabs>
  <Tab title="ESX 1.10.7">
    1. Télécharge le script et extrais-le dans tes resources.
    2. Télécharge `jaksam_core` et extrais-le dans tes resources.
    3. Ajoute le code suivant **juste après** `es_extended` dans ton `server.cfg` :

    ```cfg
    add_unsafe_worker_permission jaksam_inventory # Permet à l'inventaire de jaksam de s'installer automatiquement
    ensure jaksam_inventory
    ```

    4. Dans `es_extended/config.lua`, mets :

    ```lua
    Config.OxInventory = false
    ```

    5. Dans `es_extended/config.lua`, mets :

    ```lua
    Config.EnableDefaultInventory = false
    ```

    6. Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `jaksam_inventory/sql/`.

    ### Exemple d'ordre de démarrage

    ```cfg
    # OX
    ensure oxmysql
    ensure ox_lib
    
    ## ESX
    ensure es_extended
    ensure jaksam_inventory
    
    # Autres scripts ESX
    start [core]
    ```

    <Warning>
      Si ça ne fonctionne pas, assure-toi d'utiliser la dernière version officielle d'ESX avec toutes les dépendances nécessaires.
    </Warning>
  </Tab>
  <Tab title="ESX 1.11.3+">
    1. Télécharge le script et extrais-le dans tes resources.
    2. Télécharge `jaksam_core` et extrais-le dans tes resources.
    3. Ajoute le code suivant **juste après** `es_extended` dans ton `server.cfg` :

    ```cfg
    add_unsafe_worker_permission jaksam_inventory # Permet à l'inventaire de jaksam de s'installer automatiquement
    ensure jaksam_inventory
    ```

    4. Dans `es_extended/config.lua`, mets :

    ```lua
    Config.CustomInventory = "jaksam_inventory"
    ```

    5. Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `jaksam_inventory/sql/`.

    ### Exemple d'ordre de démarrage

    ```cfg
    # OX
    ensure oxmysql
    ensure ox_lib
    
    ## ESX
    ensure es_extended
    ensure jaksam_inventory
    
    # Autres scripts ESX
    start [core]
    ```
  </Tab>
  <Tab title="ESX 1.14.0+">
    1. Télécharge le script et extrais-le dans tes resources.
    2. Télécharge `jaksam_core` et extrais-le dans tes resources.
    3. Ajoute le code suivant **juste après** `es_extended` dans ton `server.cfg` :

    ```cfg
    add_unsafe_worker_permission jaksam_inventory # Permet à l'inventaire de jaksam de s'installer automatiquement
    ensure jaksam_inventory
    ```

    4. Dans `es_extended/shared/config/main.lua`, mets :

    ```lua
    Config.CustomInventory = "jaksam_inventory"
    ```

    5. Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `jaksam_inventory/sql/`.

    ### Exemple d'ordre de démarrage

    ```cfg
    # OX
    ensure oxmysql
    ensure ox_lib
    
    ## ESX
    ensure es_extended
    ensure jaksam_inventory
    
    # Autres scripts ESX
    start [core] ## Change "ensure" en "start" pour ne pas redémarrer es_extended
    ```
  </Tab>
  <Tab title="QBCore">
    1. Télécharge le script et extrais-le dans tes resources.
    2. Télécharge `jaksam_core` et extrais-le dans tes resources.
    3. Active `Integrations.backwardsCompatibility` pour `qb-inventory` dans `jaksam_inventory/integrations/sv_integrations.lua`.
    4. Ajoute le code suivant **juste après** `qb-core` dans ton `server.cfg` :

    ```cfg
    add_unsafe_worker_permission jaksam_inventory # Permet à l'inventaire de jaksam de s'installer automatiquement
    ensure jaksam_inventory
    ```

    5. Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `jaksam_inventory/sql/`.

    ### Exemple d'ordre de démarrage

    ```cfg
    # OX
    ensure oxmysql
    ensure ox_lib
    
    ## QBCore
    ensure qb-core
    ensure jaksam_inventory
    
    # Autres scripts QBCore
    start [qb] ## Si c'était "ensure", change en "start" pour ne pas redémarrer qb-core
    ```

    <Warning>
      Si ça ne fonctionne pas, assure-toi d'utiliser la dernière version officielle de QBCore avec toutes les dépendances nécessaires.
    </Warning>
  </Tab>
  <Tab title="QBX">
    1. Télécharge le script et extrais-le dans tes resources.
    2. Télécharge `jaksam_core` et extrais-le dans tes resources.
    3. Active `Integrations.backwardsCompatibility` pour `ox_inventory` dans `jaksam_inventory/integrations/sv_integrations.lua`.
    4. Ajoute le code suivant **juste après** `qbx_core` dans ton `server.cfg` :

    ```cfg
    add_unsafe_worker_permission jaksam_inventory # Permet à l'inventaire de jaksam de s'installer automatiquement
    ensure jaksam_inventory
    ```

    5. Le script configurera la base de données **automatiquement**. S'il ne le fait pas, tu peux exécuter manuellement les fichiers du dossier `jaksam_inventory/sql/`.

    ### Exemple d'ordre de démarrage

    ```cfg
    # OX
    ensure oxmysql
    ensure ox_lib
    
    ## QBX
    ensure qbx_core
    ensure jaksam_inventory
    
    # Autres scripts QBX
    ```

    <Warning>
      Si ça ne fonctionne pas, assure-toi d'utiliser la dernière version officielle de QBX avec toutes les dépendances nécessaires.
    </Warning>
  </Tab>
</Tabs>

Tu es prêt ! Profite bien du script 😁

## Vérification

Utilise la commande `/inventory` en jeu. Si ton inventaire s'ouvre, le script fonctionne correctement.

## Importer les anciens items et inventaires

<Tabs>
  <Tab title="ESX">
    1. Va en jeu.
    2. Utilise la commande `/inventory` et va dans **Settings**.
    3. Clique sur **Import from ESX**.
    4. C'est fait !
  </Tab>
  <Tab title="QBCore">
    1. Uniquement pendant ce processus, assure-toi que **l'original `qb-inventory`** est en cours d'exécution. Après l'import, tu peux et devrais le retirer.
    2. Utilise la commande `/inventory` et va dans **Settings**.
    3. Clique sur **Import from QBCore**.
    4. C'est fait !
  </Tab>
  <Tab title="OX Inventory">
    1. Uniquement pendant ce processus, assure-toi que `ox_inventory` est en cours d'exécution. Après l'import, tu peux et devrais le retirer.
    2. Utilise la commande `/inventory` et va dans **Settings**.
    3. Clique sur **Import from OX inventory**.
    4. C'est fait !
  </Tab>
  <Tab title="qs-inventory">
    1. Uniquement pendant ce processus, assure-toi que `qs-inventory` est en cours d'exécution. Après l'import, tu peux et devrais le retirer.
    2. Utilise la commande `/inventory` et va dans **Settings**.
    3. Clique sur **Import from qs-inventory**.
    4. C'est fait !
  </Tab>
  <Tab title="Chezza Inventory">
    1. Uniquement pendant ce processus, assure-toi que **l'inventaire Chezza** est en cours d'exécution. Après l'import, tu peux et devrais le retirer.
    2. Utilise la commande `/inventory` et va dans **Settings**.
    3. Clique sur **Import from Chezza inventory**.
    4. C'est fait !
  </Tab>
  <Tab title="TGiann Inventory">
    1. Uniquement pendant ce processus, assure-toi que **l'inventaire TGiann** est en cours d'exécution. Après l'import, tu peux et devrais le retirer.
    2. Utilise la commande `/inventory` et va dans **Settings**.
    3. Clique sur **Import from TGiann inventory**.
    4. C'est fait !
  </Tab>
</Tabs>

## Rétrocompatibilité

Cet inventaire te permet d'utiliser tes anciens scripts, même s'ils nécessitent un système d'inventaire différent.

### Fonctions par défaut du framework

Tu peux utiliser les fonctions d'inventaire normales fournies par ton framework.

### Compatibilité OX Inventory

Si tes anciens scripts utilisent **OX Inventory**, tu peux activer une compatibilité simple.

1. Va dans `jaksam_inventory/integrations/sv_integrations.lua`.
2. Active `ox_inventory` dans `Integrations.backwardsCompatibility`.
3. Le serveur peut nécessiter un redémarrage après son premier chargement avec ces paramètres.

### Compatibilité QB Inventory

Si tes anciens scripts utilisent **QB Inventory**, tu peux activer une compatibilité simple.

1. Va dans `jaksam_inventory/integrations/sv_integrations.lua`.
2. Active `qb-inventory` dans `Integrations.backwardsCompatibility`.
3. Le serveur peut nécessiter un redémarrage après son premier chargement avec ces paramètres.

C'est tout ! Tes anciens scripts devraient maintenant fonctionner avec cet inventaire.
