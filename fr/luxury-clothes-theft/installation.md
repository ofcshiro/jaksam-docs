---
title: "Installation"
description: "Installe Luxury Clothes Theft sur ton serveur FiveM avec ESX ou QBCore, incluant la configuration optionnelle des items par défaut."
icon: "download"
---

L'installation du script est extrêmement simple.

## Prérequis

- **ESX** ou **QBCore**
- Sur QBCore, le script [`menu_default`](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing)

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
      <Step title="Configure les options">
        Configure les options dans les fichiers de config (lis bien les commentaires, ils expliquent tout).
      </Step>
    </Steps>

    ### Ajouter des items — Optionnel

    Pour ajouter les items prédéfinis, il te suffit d'exécuter le fichier `luxury_clothes_theft/sql/items_limit.sql` **ou** `luxury_clothes_theft/sql/items_weight.sql`, selon que ton serveur utilise limit ou weight.

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
      <Step title="Configure les options">
        Configure les options dans les fichiers de config (lis bien les commentaires, ils expliquent tout).
      </Step>
      <Step title="Installe menu_default">
        Télécharge et extrais le script [menu_default](https://drive.google.com/file/d/1Ezz-d50NIKQZeZJ-RgyclvNG7qC4Nfu8/view?usp=sharing) dans tes resources, **sans le renommer**, et ajoute-le à ton auto start (exemple : `server.cfg`).
      </Step>
    </Steps>

    ### Ajouter des items

    Pour ajouter les nouveaux items, modifie le fichier `qb-core/shared/items.lua` et ajoute le code suivant en bas de la table :

    ```lua
    ['luxury_stolen_bag'] = {['name'] = 'luxury_stolen_bag', ['label'] = 'Luxury clothes bag', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['gucci_tshirt'] = {['name'] = 'gucci_tshirt', ['label'] = 'Gucci T-Shirt', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['gucci_flipflops'] = {['name'] = 'gucci_flipflops', ['label'] = 'Gucci Flip Flops', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['louis_vuitton_bag'] = {['name'] = 'louis_vuitton_bag', ['label'] = 'Louis Vuitton Bag', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['louis_vuitton_tshirt'] = {['name'] = 'louis_vuitton_tshirt', ['label'] = 'Louis Vuitton T-Shirt', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['valentino_pants'] = {['name'] = 'valentino_pants', ['label'] = 'Valentino Pants', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['prada_shoes'] = {['name'] = 'prada_shoes', ['label'] = 'Prada Shoes', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ['prada_bag'] = {['name'] = 'prada_bag', ['label'] = 'Prada Bag', ['weight'] = 500, ['type'] = 'item', ['image'] = 'your_image.png', ['unique'] = false, ['useable'] = false, ['shouldClose'] = false, ['combinable'] = nil},
    ```

    <Frame caption="Exemple de capture d'écran">
      ![QBCore Luxury Clothes Theft items example](/images/qb_core_luxury_clothest_theft_items.jpg)
    </Frame>
  </Tab>
</Tabs>

Tu es prêt ! Profite bien du script 😁

## Vérification

<Info>
  \[TODO : INFORMATION NÉCESSAIRE\] Aucune vérification in-game pour une installation réussie n'est encore documentée pour Luxury Clothes Theft.
</Info>
