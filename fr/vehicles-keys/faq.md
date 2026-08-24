---
title: "FAQ"
description: "Questions fréquemment posées spécifiques à Vehicles Keys."
icon: "circle-question"
---

Cette page contient les FAQ liées **uniquement à ce script** — pense aussi à consulter la [FAQ commune](/fr/jaksams-scripts/common-faq) pour les autres problèmes.

<AccordionGroup>
  <Accordion title="Avertissement de saccades / Performance">
    Si ton serveur montre des saccades/problèmes de performance, c'est parce que l'option `CONTINUOUSLY_REFRESH_PLAYERS_OWNED_VEHICLES` est activée dans `vehicles_keys/integrations/sv_integrations.lua`.

    Si tu désactives l'option, elle ne causera plus de problèmes de performance, mais tu devras utiliser les exports de la documentation pour actualiser les véhicules possédés par un joueur (par exemple après qu'il ait acheté un nouveau véhicule dans une boutique).

    Consulte la page [fix hotwiring bought car](/fr/vehicles-keys/fix-hotwiring-bought-car) pour des **exemples** déjà prêts.

    <Note>
      L'intégration avec d'autres scripts externes dépend entièrement de toi.
    </Note>
  </Accordion>

  <Accordion title="Impossible d'entrer dans le véhicule">
    Si tu ne peux pas entrer dans un véhicule après avoir détruit sa vitre, cela signifie que tu as encore le script `qb-vehicleskeys` démarré.

    Retire-le pour résoudre le problème.
  </Accordion>
</AccordionGroup>
