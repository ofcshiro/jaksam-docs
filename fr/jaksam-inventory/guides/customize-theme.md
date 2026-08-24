---
title: "Personnaliser le thème par défaut"
description: "Définis un thème par défaut personnalisé pour tous les joueurs de ton serveur, étape par étape"
icon: "palette"
---

Tu veux que chaque joueur ait le même thème par défaut ? Voici comment faire, étape par étape.

<Steps>
  <Step title="Ouvre ton inventaire">
    Appuie sur **F2** en jeu pour ouvrir ton inventaire.
  </Step>
  <Step title="Ouvre l'éditeur de thème">
    Clique sur le bouton **Theme** (en bas à droite).

    <Frame>
      ![Inventory theme customization 1](/images/inventory-theme-1.jpg)
    </Frame>
  </Step>
  <Step title="Personnalise et sauvegarde">
    Change les couleurs et styles comme tu veux, puis clique sur **Save**.
  </Step>
  <Step title="Sélectionne ton thème">
    Assure-toi que ton thème personnalisé est sélectionné.

    <Frame>
      ![Inventory theme customization 2](/images/inventory-theme-2.jpg)
    </Frame>
  </Step>
  <Step title="Ouvre la console">
    Appuie sur **F8** pour ouvrir la console, puis tape :

    ```bash
        admintheme
    ```
  </Step>
  <Step title="Copie le code du thème">
    Tu verras un bloc de code.

    <Note>
      Copie _tout_ entre `COPY FROM THE LINE BELOW` et `COPY TILL THE LINE ABOVE` — n'oublie pas les bords.
    </Note>

    <Frame>
      ![Inventory theme customization 3](/images/inventory-theme-3.jpg)
    </Frame>
  </Step>
  <Step title="Ouvre le fichier de thème">
    Va dans les fichiers du serveur et ouvre :

    ```text
        jaksam_inventory/dist/assets/variables.css
    ```
  </Step>
  <Step title="Colle et remplace">
    Colle ce que tu as copié, en remplaçant **tout** le contenu de ce fichier.
  </Step>
  <Step title="Redémarre">
    Redémarre le script ou recharge le serveur.
  </Step>
</Steps>

<Tip>
  C'est tout ! Maintenant, le thème par défaut de tout le monde utilisera tes couleurs et paramètres personnalisés (sauf si le joueur le change lui-même).
</Tip>
