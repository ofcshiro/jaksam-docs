---
title: "Métadonnées"
icon: "tags"
description: "Affiche les métadonnées des items aux joueurs et définis des valeurs de métadonnées par défaut ou dynamiques"
---

## Comment afficher les métadonnées aux joueurs

Afficher des métadonnées spécifiques aux joueurs est simple. Tout d'abord, tu dois connaître la clé de métadonnée que tu veux afficher. Pour cela, tu peux activer le "Debug mode" dans le menu de paramètres `/inventory`, puis survoler l'item dont tu veux voir les métadonnées.

<Columns cols={2}>
  <Frame>
    ![Item debug settings screenshot](/images/metadata-debug-settings.png)
  </Frame>

  <Frame>
    ![Item debug metadata screenshot](/images/metadata-debug-item.png)
  </Frame>
</Columns>

### L'ajouter à un seul item

Pour montrer aux joueurs les métadonnées d'un seul item, tu peux ajouter et adapter ce code dans la définition de l'item, dans le fichier `jaksam_inventory/_data/items.lua` :

```lua
displayFields = {
    { field = 'YOUR_METADATA_KEY_HERE', label = 'TEXT YOU WANT HERE: ${value}'}, -- Exemple aléatoire
    { field = 'ammo', label = 'Ammo: ${value}'}, -- Utile sur les armes (déjà intégré par défaut)
    { field = 'plate', label = 'Plate: ${value}'}, -- Utile sur les clés de véhicule
},
```

<Frame>
  ![Single item display fields example](/images/metadata-single-item-example.png)
</Frame>

### L'ajouter à tous les types d'items

Pour montrer aux joueurs les métadonnées de tout un type d'item, c'est exactement la même méthode, mais place-le dans la table `Script.defaultsByType`, dans le fichier `jaksam_inventory/_data/defaults.lua`.

### Optionnel : rendre les valeurs de métadonnées plus jolies

Parfois tu veux afficher les métadonnées de manière plus jolie aux joueurs. Par exemple, au lieu d'afficher "weapon_pistol", tu veux afficher "Pistol". C'est là qu'interviennent les formatters !

<Tip>
  Un formatter est comme un traducteur : il prend la valeur d'origine (par exemple `weapon_pistol`) et la convertit en quelque chose de plus joli (par exemple `Pistol`).
</Tip>

Tu peux utiliser les formatters intégrés ou en créer des personnalisés dans `jaksam_inventory/_data/formatter.lua`. Voici comment les utiliser :

```lua
displayFields = {
    { field = 'item', label = 'Label: ${value}', formatterId = "itemNameToLabel"}, -- Un exemple avec un formatter intégré
},
```

## Comment définir des métadonnées par défaut pour les items

Tu veux que les items aient certaines valeurs de métadonnées lors de leur création ? Par exemple, peut-être veux-tu que les nouvelles armes commencent avec 50% de durabilité. Voici comment faire :

<Steps>
  <Step title="Ouvre le menu admin">
    Tape `/inventory` en jeu pour ouvrir le menu admin.
  </Step>
  <Step title="Trouve l'item">
    Trouve et clique sur l'item que tu veux modifier.
  </Step>
  <Step title="Ouvre l'onglet metadata">
    Clique sur l'onglet "metadata".
  </Step>
  <Step title="Définis les valeurs">
    Définis les valeurs de métadonnées que tu veux.
  </Step>
</Steps>

### Avancé - Utiliser des templates pour des métadonnées dynamiques

Parfois tu veux des métadonnées qui changent selon certaines conditions. Pour cela, tu peux utiliser des templates :

<Steps>
  <Step title="Ouvre l'onglet metadata">
    Va dans le même onglet metadata dans l'éditeur d'item.
  </Step>
  <Step title="Passe au type template">
    Change le type de métadonnée en `template`.
  </Step>
  <Step title="Choisis ou crée un template">
    Sélectionne un template existant, ou crée le tien dans `jaksam_inventory/_data/metadata_templates.lua`.
  </Step>
</Steps>

Les templates te permettent de créer des métadonnées qui se mettent à jour automatiquement selon des règles que tu définis !

#### Exemple

Quelques exemples de ce que tu peux faire avec des templates de métadonnées dynamiques :

- Attribuer à la carte d'identité d'un joueur son nom, sa date de naissance, sa taille, etc.
- Attribuer une durabilité aléatoire à une arme
- Attribuer la date de création à un item (la première fois qu'il est créé)
