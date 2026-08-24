---
title: "Injection des jobs QBCore"
description: "Corrige le problème d'autres scripts qui ne reconnaissent pas les jobs de Jobs Creator sur QBCore à cause de l'ordre de démarrage des scripts."
icon: "plug"
---

Normalement tu n'as besoin d'ajouter aucun code. Malgré cela, des ordres de démarrage de scripts différents peuvent faire en sorte que d'autres scripts ne reconnaissent pas les jobs de Jobs Creator sur QBCore.

## Comment puis-je corriger ça ?

La solution est très simple — ajoute l'event suivant côté client et côté serveur dans le script qui ne reconnaît pas les jobs de Jobs Creator :

```lua
-- Intégration jaksam's Jobs Creator
AddEventHandler('jobs_creator:injectJobs', function(jobs)
    -- Assigne les nouveaux jobs à l'objet QBCore, la ligne suivante dépend de la structure de ton script
    QBCore.Shared.Jobs = jobs
end)
```
