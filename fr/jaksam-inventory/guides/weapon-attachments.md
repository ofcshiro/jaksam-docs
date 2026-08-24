---
title: "Accessoires d'armes"
icon: "gun"
description: "Associe plusieurs IDs de composants d'armes à un seul item d'accessoire"
---

## Pourquoi ce guide existe

Dans GTA V, chaque arme a des IDs de composants différents pour le même type d'accessoire. Par exemple :

- Un silencieux pour un Pistol utilise `COMPONENT_AT_PI_SUPP`
- Un silencieux pour un Combat Pistol utilise `COMPONENT_AT_PI_SUPP_02`

**Le système d'inventaire simplifie ça :** tu peux créer UN seul item (comme "suppressor") qui fonctionne automatiquement avec toutes les armes compatibles en associant plusieurs IDs de composants à celui-ci.

## Guide étape par étape

### Étape 1 : vérifier si l'item existe

D'abord, vérifie si un item pour ton type d'accessoire existe déjà dans ta base de données.

<Tabs>
  <Tab title="Armes GTA vanilla">
    - Les accessoires les plus courants (silencieux, chargeur étendu, lampe torche, etc.) devraient déjà exister
    - Utilise la commande `/inventory` en jeu pour vérifier les items existants
  </Tab>
  <Tab title="Armes moddées">
    - Tu devras créer un nouvel item OU ajouter le hash de composant de l'arme moddée à un item existant
    - Exemple : si tu as un AK47 moddé avec un silencieux, tu peux ajouter son hash de silencieux à l'item "suppressor" existant
  </Tab>
</Tabs>

**Créer/modifier l'item :**

<Steps>
  <Step title="Ouvre l'interface de gestion de l'inventaire">
    Tape `/inventory` en jeu.
  </Step>
  <Step title="Crée ou modifie un item">
    Crée un nouvel item ou modifie un item existant.
  </Step>
  <Step title="Définis le bon type d'item">
    <CardGroup cols={2}>
      <Card title="barrel">
        Silencieux, frein de bouche
      </Card>

      <Card title="clip">
        Chargeurs
      </Card>

      <Card title="scope">
        Lunettes et optiques
      </Card>

      <Card title="flashlight">
        Lampes tactiques
      </Card>

      <Card title="grip">
        Poignées avant
      </Card>
    </CardGroup>

    <Frame caption="Exemple avec le silencieux par défaut">
      ![Edit default suppressor item component example](/images/weapon-attachments-item-example.jpg)
    </Frame>
  </Step>
</Steps>

### Étape 2 : ajouter les hashs de composants

Maintenant, tu dois ajouter le(s) hash(s) de composant auquel cet item doit s'appliquer sur les armes.

**Où trouver les hashs de composants :**

<Tabs>
  <Tab title="Armes GTA vanilla">
    - Consulte le [wiki](https://docs.fivem.net/docs/game-references/weapon-models/)
    - Ou cherche en ligne "GTA V weapon components list"
  </Tab>
  <Tab title="Armes moddées">
    - Ton script d'arme moddée contient très probablement un fichier texte avec les hashs de composants
    - Un exemple de nom de composant : ils commencent souvent par `COMPONENT_`
    - Contacte le créateur de l'arme ou sa documentation si tu ne le trouves pas
  </Tab>
</Tabs>

**Comment les ajouter :**

<Steps>
  <Step title="Ouvre la section Component Hashes">
    Dans l'écran de modification de l'item d'accessoire, trouve la section "Component Hashes".
  </Step>
  <Step title="Ajoute un hash">
    Clique sur "Add Component Hash".
  </Step>
  <Step title="Entre le hash">
    Entre le hash du composant (par exemple `COMPONENT_AT_PI_SUPP`).
  </Step>
  <Step title="Répète">
    Répète pour tous les composants avec lesquels tu veux que cet accessoire fonctionne.
  </Step>
</Steps>

<Info>
  Le menu te montrera quelles armes sont compatibles avec chaque hash de composant que tu ajoutes.
</Info>

<Frame caption="Exemple de liste de hashs d'item">
  ![Edit item hashes list example](/images/weapon-attachments-hashes-example.jpg)
</Frame>

### Étape 3 : tester en jeu

<Steps>
  <Step title="Donne-toi l'item">
    `/giveitem [your_id] [item_name] 1` ou via l'omnipack (`F1` avec l'inventaire ouvert).
  </Step>
  <Step title="Donne-toi une arme">
    Donne-toi une arme compatible.
  </Step>
  <Step title="Attache-le">
    Essaie d'attacher le composant.
  </Step>
</Steps>

<Tip>
  C'est tout ! Le système appliquera automatiquement le bon composant selon l'arme.
</Tip>

## Exemple complet

Disons que tu veux ajouter un silencieux pour une arme moddée appelée "WEAPON_MODDEDAK47" :

<Steps>
  <Step title="Vérifie les items existants">
    Ouvre `/inventory` et cherche "suppressor" - il existe !
  </Step>
  <Step title="Modifie l'item">
    Clique sur modifier pour l'item suppressor.
  </Step>
  <Step title="Ajoute le hash">
    Ajoute `COMPONENT_MODDEDAK47_SUPP` à la liste des hashs de composants.
  </Step>
  <Step title="Sauvegarde">
    Sauvegarde l'item.
  </Step>
  <Step title="Teste">
    Donne-toi le silencieux et l'AK47 moddé, puis essaie de l'attacher.
  </Step>
</Steps>
