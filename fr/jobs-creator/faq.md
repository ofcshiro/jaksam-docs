---
title: "FAQ"
description: "Questions fréquemment posées spécifiques à Jobs Creator, couvrant les animations, les salaires, les tenues et les erreurs de configuration courantes."
icon: "circle-question"
---

Cette page contient des FAQ liées **UNIQUEMENT à ce script**. Pense à consulter aussi la [FAQ commune](/fr/jaksams-scripts/common-faq) pour les autres problèmes.

<AccordionGroup>
  <Accordion title="Comment changer les animations">
    [Voici une liste d'animations utilisables](https://alexguirre.github.io/animations-list/)

    - Le texte en gras est le dictionnaire d'animation
    - Le texte plus petit est le nom de l'animation

    [Voici la liste des scénarios utilisables](https://wiki.rage.mp/index.php?title=Scenarios)

    La principale différence entre les scénarios et les animations est qu'un scénario a généralement un objet associé à l'animation.

    _Il n'est pas possible d'utiliser des animations externes._

    <Note>
      Toutes les animations des listes ne fonctionnent pas.
    </Note>
  </Accordion>

  <Accordion title="Comment verrouiller les véhicules des jobs">
    Pour verrouiller les véhicules, tu as 2 possibilités :

    1. Utiliser les events et exports de la documentation du script pour intégrer ton propre script de verrouillage de véhicules
    2. Utiliser **jaksam's Vehicles Keys**, qui inclut déjà l'intégration avec Jobs Creator

    _Remarque : l'intégration de scripts externes est entièrement à ta charge._
  </Accordion>

  <Accordion title="Comment Jobs Creator gère-t-il les salaires ?">
    Jobs Creator ne gère pas les salaires, car c'est le script du framework qui s'en charge :

    - Pour ESX, les scripts `es_extended` et `esx_society` gèrent les salaires
    - Pour QBCore, `qb-core` gère les salaires

    Tu pourras donc **définir** les salaires dans Jobs Creator, mais c'est le framework qui verse l'argent.
  </Accordion>

  <Accordion title="Comment corriger l'erreur « Couldnt create marker »">
    Ce problème est causé par un souci dans la table `job_data` de la base de données.

    Solutions possibles :

    1. Supprime la table `job_data` de la base de données et redémarre le script/serveur
    2. Si la colonne `id` de la table `job_data` n'a pas **AUTO INCREMENT** comme valeur par défaut, configure cette colonne pour qu'elle l'ait
  </Accordion>

  <Accordion title="Pourquoi les fonctionnalités de tenues ne fonctionnent pas ?">
    Si les fonctionnalités de tenues ne fonctionnent pas, c'est parce qu'il te manque les dépendances requises :

    - Sur ESX, tu dois avoir les scripts `esx_skin` et `skinchanger` installés
    - Sur QBCore, tu dois avoir le script `qb-clothing` installé

    Jobs Creator dispose d'une intégration avec [**illenium-appearance**](https://github.com/iLLeniumStudios/illenium-appearance), qui devrait fonctionner sur les deux frameworks.
  </Accordion>

  <Accordion title="L'amélioreur d'armes ne fonctionne pas">
    Si le marqueur d'amélioration d'armes ne fonctionne pas, voici 2 raisons possibles :

    1. Tu utilises une arme addon, mais tu ne l'as pas configurée correctement dans le script `es_extended`
    2. Ton inventaire modifie le comportement standard d'**ESX/QBCore**, dans ce cas tu dois utiliser ton propre inventaire à la place de Jobs Creator pour les composants et teintes d'armes
  </Accordion>

  <Accordion title="Modifier les libellés de véhicules dans les garages">
    Jobs Creator récupère les libellés de véhicules via les natives de FiveM, donc pour avoir des libellés personnalisés, tu devras les configurer dans ton script de véhicules addon.

    Il existe plusieurs guides sur les forums FiveM sur comment configurer les noms d'affichage des véhicules addon.
  </Accordion>

  <Accordion title="QBCore ne reconnaît pas les jobs de Jobs Creator">
    Normalement tu n'as besoin d'ajouter aucun code. Malgré cela, un ordre de démarrage des scripts différent peut faire en sorte que d'autres scripts ne reconnaissent pas les jobs de Jobs Creator sur QBCore.

    **Comment puis-je corriger ça ?**

    La solution est très simple : ajoute l'event suivant **côté client et côté serveur** dans le script qui ne reconnaît pas les jobs de Jobs Creator.

    ```lua
        -- Intégration jaksam's Jobs Creator
        AddEventHandler('jobs_creator:injectJobs', function(jobs)
            -- Assigne les nouveaux jobs à l'objet QBCore, la ligne suivante dépend de la structure de ton script
            QBCore.Shared.Jobs = jobs
        end)
    ```
  </Accordion>
</AccordionGroup>
