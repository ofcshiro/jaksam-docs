---
title: "Recettes de craft (glisser-déposer)"
icon: "flask-gear"
description: "Permets aux joueurs de fabriquer des items en glissant un item sur un autre grâce au hook de craft intégré"
---

Tu veux que les joueurs puissent fabriquer des items en glissant un item sur un autre ? Ce guide te montre comment faire, étape par étape.

Cette fonctionnalité permet aux joueurs de fabriquer des items en glissant un item source sur un item cible dans le même inventaire. Quand la recette correspond, les items sont combinés et le résultat est créé.

<Note>
  Cette fonctionnalité est fournie par le hook `_hooks/sv_craftings.lua`. Tu as juste besoin d'ajouter tes recettes à la table `CRAFTING_RECIPES`.
</Note>

## Comment ça marche

<Steps>
  <Step title="Glisse la source sur la cible">
    Le joueur glisse un **item source** sur un **item cible** dans le même inventaire.
  </Step>
  <Step title="Vérification de la recette">
    Le système vérifie s'il existe une recette correspondante.
  </Step>
  <Step title="Le craft se produit">
    Si la recette correspond et que les quantités sont suffisantes, le craft se produit.
  </Step>
  <Step title="Les items sont consommés">
    Les items source et/ou cible sont retirés (selon les paramètres de la recette).
  </Step>
  <Step title="Le résultat est ajouté">
    L'item résultat est ajouté à l'inventaire.
  </Step>
</Steps>

## Guide étape par étape

<Steps>
  <Step title="Ouvre le hook de craft">
    Va dans : `jaksam_inventory/_hooks/sv_craftings.lua`
  </Step>
  <Step title="Trouve la table des recettes">
    Trouve la table `CRAFTING_RECIPES` (elle se trouve près du haut du fichier).
  </Step>
  <Step title="Ajoute ta recette">
    Ajoute ta recette en suivant ce format :

    ```lua
        local CRAFTING_RECIPES = {
            ["source_item_name"] = {
                sourceQuantityRequired = 1,        -- Combien d'items source sont nécessaires
                sourceIsToRemove = true,           -- Retirer l'item source après le craft ?
                targetItem = "target_item_name",  -- Nom de l'item cible
                targetQuantity = 1,                -- Combien d'items cibles sont nécessaires
                targetIsToRemove = true,           -- Retirer l'item cible après le craft ?
                resultItem = "result_item_name",  -- Nom de l'item créé
                resultQuantity = 1,                -- Combien d'items résultats sont créés
            },
        }
    ```
  </Step>
  <Step title="Redémarre">
    Sauvegarde le fichier et redémarre le script/recharge le serveur.
  </Step>
</Steps>

<Tip>
  C'est tout ! Maintenant les joueurs peuvent glisser l'item source sur l'item cible pour fabriquer.
</Tip>

## Explication des propriétés de la recette

<ParamField path="sourceQuantityRequired" type="number">
  Combien d'items source sont nécessaires pour la recette
</ParamField>

<ParamField path="sourceIsToRemove" type="boolean">
  Mets `true` si l'item source doit être retiré après le craft, `false` pour le garder
</ParamField>

<ParamField path="targetItem" type="string">
  Le nom exact (tel que défini dans `items.lua`) de l'item sur lequel tu glisses l'item source
</ParamField>

<ParamField path="targetQuantity" type="number">
  Combien d'items cibles sont nécessaires pour la recette
</ParamField>

<ParamField path="targetIsToRemove" type="boolean">
  Mets `true` si l'item cible doit être retiré après le craft, `false` pour le garder
</ParamField>

<ParamField path="resultItem" type="string">
  Le nom exact (tel que défini dans `items.lua`) de l'item qui sera créé
</ParamField>

<ParamField path="resultQuantity" type="number">
  Combien d'items résultats seront créés
</ParamField>

## Exemples

<Tabs>
  <Tab title="Améliorer une lunette en thermique">
    Combine une clé à molette avec une lunette avancée pour créer une lunette thermique :

    ```lua
        ["weapon_wrench"] = {
            sourceQuantityRequired = 1,
            sourceIsToRemove = false,              -- Garde la clé à molette (outil réutilisable)
            targetItem = "advanced_scope",
            targetQuantity = 1,
            targetIsToRemove = true,               -- Retire la lunette avancée
            resultItem = "thermal_scope",
            resultQuantity = 1,
        },
    ```

    **Comment l'utiliser :** glisse la clé à molette sur la lunette avancée → la lunette thermique est créée, la clé à molette reste, la lunette avancée est retirée.
  </Tab>
  <Tab title="Combiner des matériaux">
    Combine 2 morceaux de bois avec 1 clou pour créer une planche en bois :

    ```lua
        ["wood"] = {
            sourceQuantityRequired = 2,
            sourceIsToRemove = true,               -- Retire les 2 morceaux de bois
            targetItem = "nail",
            targetQuantity = 1,
            targetIsToRemove = true,               -- Retire le clou
            resultItem = "wooden_plank",
            resultQuantity = 1,
        },
    ```

    **Comment l'utiliser :** glisse 2 items bois sur 1 clou → la planche en bois est créée, les deux matériaux sont consommés.
  </Tab>
</Tabs>

## Notes importantes

<CardGroup cols={2}>
  <Card title="Même inventaire uniquement" icon="box">
    Le craft ne fonctionne que quand les deux items sont dans le **même inventaire** (tu ne peux pas glisser depuis l'inventaire du joueur vers l'inventaire d'un véhicule)
  </Card>

  <Card title="Les noms d'items doivent correspondre" icon="fingerprint">
    Les noms `targetItem` et `resultItem` doivent correspondre exactement aux noms d'items dans `_data/items.lua`
  </Card>

  <Card title="Vérification des quantités" icon="calculator">
    Le système vérifie automatiquement si tu as assez d'items avant de fabriquer
  </Card>

  <Card title="Plusieurs recettes" icon="layer-group">
    Tu peux ajouter autant de recettes que tu veux à la table `CRAFTING_RECIPES`
  </Card>
</CardGroup>

<Warning>
  **Une source, plusieurs cibles :** chaque item source ne peut avoir qu'une seule recette. Si tu as besoin de plusieurs recettes pour le même item source, tu devras utiliser des items source différents ou créer des systèmes de craft séparés.
</Warning>
