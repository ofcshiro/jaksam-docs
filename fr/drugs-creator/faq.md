---
title: "FAQ"
description: "Questions fréquemment posées propres à Drugs Creator."
icon: "circle-question"
---

Cette page contient des FAQ concernant **uniquement ce script** — pense aussi à consulter la [FAQ commune](/fr/jaksams-scripts/common-faq) pour les autres problèmes.

<AccordionGroup>
  <Accordion title="Les effets des drogues ne fonctionnent pas">
    Si les effets ne fonctionnent pas, cela signifie que la fonction `ESX.RegisterUsableItem` de ton `es_extended` ne fonctionne pas correctement.

    Tu peux toujours enregistrer/déclencher les effets manuellement en utilisant l'event [manually start drugs effects](/fr/drugs-creator/client/manually-start-drugs-effects).

    Sur **ESX** comme sur **QBCore**, un anticheat peut interférer avec les effets des drogues.

    <Note>
      Cela ne dépend pas du script, et nous ne pouvons pas résoudre ce problème pour toi.
    </Note>
  </Accordion>

  <Accordion title="Mauvaises performances">
    Si tu rencontres des problèmes de performances côté serveur avec Drugs Creator, c'est très probablement à cause de la vente aux PNJ, qui nécessite de rafraîchir l'inventaire de tous les joueurs pour pouvoir afficher le dialogue `Press E to sell drugs`.

    Pour améliorer les performances, active l'option correspondante dans les paramètres ingame du script, afin qu'il utilise le PNJ le plus proche ou en fasse apparaître un (selon ta configuration).
  </Accordion>
</AccordionGroup>
