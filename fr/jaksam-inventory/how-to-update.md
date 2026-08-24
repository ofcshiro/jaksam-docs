---
title: "Comment faire"
icon: "rectangle-new"
tag: "Update"
description: "Garde ton installation de Jaksam Inventory à jour sans perdre tes items personnalisés, paramètres, intégrations ou autres personnalisations."
---

# Mettre à jour Jaksam Inventory

<Warning>
  **Crée toujours une sauvegarde avant de mettre à jour.** Ne supprime jamais ton installation existante avant d'avoir une sauvegarde fonctionnelle.
</Warning>

## Avant de commencer

<Tip>
  **Recommandé :** Garde ta sauvegarde pendant au moins quelques jours après la mise à jour. Cela facilite un retour en arrière si quelque chose ne va pas.
</Tip>

<CardGroup cols={2}>
  <Card title="Arrête ton serveur" icon="server">
    Arrête toujours ton serveur FiveM avant de remplacer les fichiers de l'inventaire.
  </Card>

  <Card title="Crée une sauvegarde" icon="floppy-disk">
    Sauvegarde tes fichiers et dossiers personnalisés avant d'installer la nouvelle version.
  </Card>

  <Card title="Installe la mise à jour" icon="download">
    Retire l'ancienne version et upload la dernière version de Jaksam Inventory.
  </Card>

  <Card title="Restaure tes personnalisations" icon="rotate">
    Restaure tes fichiers sauvegardés dans la nouvelle installation.
  </Card>
</CardGroup>

## Que dois-je sauvegarder ?

### Toujours sauvegarder

Ces fichiers et dossiers doivent **toujours** être inclus dans ta sauvegarde :

| Fichier / Dossier | Description |
| --- | --- |
| `_data/` | Items et paramètres d'inventaire |
| `_backups/` | Sauvegardes de la liste d'items |
| `_hooks/` | Recettes de craft et logique personnalisée |
| `_modules/` | Intégrations avec des scripts externes |
| `integrations/` | Paramètres d'intégration |
| `current_config.json` | Fichier de configuration principal |

### Fichiers personnalisés

Ne sauvegarde ceux-ci que si tu les as modifiés ou ajoutés :

| Fichier / Dossier | Description |
| --- | --- |
| `_images/` | Images d'items personnalisées |
| `dist/assets/variables.css` | Couleurs de thème personnalisées |
| `_locales/` | Traductions personnalisées |
| `dist/menu_translations/` | Traductions de menu personnalisées |

<Note>
  Si tu n'as personnalisé aucun des fichiers listés ci-dessus, tu n'as pas besoin de les sauvegarder.
</Note>

## Processus de mise à jour

Suis ces étapes **dans l'ordre**.

## Référence rapide

| Fichier / Dossier | Sauvegarde requise | Utilité |
| --- | :-: | --- |
| `_data/` | Oui | Items et paramètres |
| `_backups/` | Oui | Sauvegardes de la liste d'items |
| `_hooks/` | Oui | Craft et logique personnalisée |
| `_modules/` | Oui | Intégrations externes |
| `integrations/` | Oui | Paramètres d'intégration |
| `current_config.json` | Oui | Configuration principale |
| `_images/` | Personnalisé | Images d'items personnalisées |
| `dist/assets/variables.css` | Personnalisé | Personnalisation du thème |
| `_locales/` | Personnalisé | Traductions personnalisées |
| `dist/menu_translations/` | Personnalisé | Traductions de menu |

## Dépannage

<AccordionGroup>
  <Accordion title="Mes items ont disparu">
    Restaure le dossier `_data/` depuis ta sauvegarde et redémarre le serveur.
  </Accordion>

  <Accordion title="Mes recettes de craft manquent">
    Restaure le dossier `_hooks/` depuis ta sauvegarde.
  </Accordion>

  <Accordion title="Mes paramètres ont été réinitialisés">
    Restaure `current_config.json` depuis ta sauvegarde.
  </Accordion>

  <Accordion title="Les couleurs de mon thème ont été réinitialisées">
    Restaure `dist/assets/variables.css` depuis ta sauvegarde si tu as personnalisé le thème par défaut.
  </Accordion>

  <Accordion title="Mes images personnalisées manquent">
    Restaure ton dossier `_images/` personnalisé.
  </Accordion>

  <Accordion title="Mes traductions manquent">
    Restaure `_locales/` et/ou `dist/menu_translations/`, selon les fichiers de traduction que tu as personnalisés.
  </Accordion>

  <Accordion title="Mon serveur ne démarre pas">
    1. Assure-toi que le nouveau dossier `jaksam_inventory` est correctement installé.
    2. Assure-toi que tes fichiers de sauvegarde ont été restaurés aux bons emplacements.
    3. Attends environ 30 secondes après le démarrage du serveur, car la base de données peut être en train de se mettre à jour automatiquement.
    4. Vérifie la console de ton serveur pour d'éventuelles erreurs.
    5. Si le problème persiste, restaure ta sauvegarde précédente et contacte le support.
  </Accordion>
</AccordionGroup>

## Important

<Warning>
  **Ne supprime jamais ta sauvegarde immédiatement après une mise à jour réussie.** Garde-la quelques jours au cas où tu découvrirais un problème plus tard.
</Warning>

<Check>
  Une fois que tout fonctionne correctement, ta mise à jour de Jaksam Inventory est terminée.
</Check>
