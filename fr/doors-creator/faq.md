---
title: "FAQ"
description: "Questions fréquemment posées spécifiques à Doors Creator."
icon: "circle-question"
---

Cette page contient les FAQ liées **uniquement à ce script** — pense aussi à consulter la [FAQ commune](/fr/jaksams-scripts/common-faq) pour les autres problèmes.

<AccordionGroup>
  <Accordion title="Impossible de sélectionner une porte">
    Si tu ne peux pas sélectionner une porte, cela signifie que le modèle de la porte n'est pas dans la liste des portes autorisées.

    Pour ajouter le modèle de la porte à la liste, appuie sur **H** pendant que tu sélectionnes la porte.

    Si tu n'arrives toujours pas à sélectionner la porte après avoir appuyé sur H, voici les raisons possibles :

    - Tu as un script qui ajoute une arme à ton personnage
    - La porte n'est pas utilisable pour une raison quelconque — si c'est un MLO modifié, c'est probablement la cause
  </Accordion>

  <Accordion title="La porte de coffre ne fonctionne pas">
    Si une porte en particulier ne fonctionne pas avec l'option coffre, essaie **les deux** options ratio et heading.

    Pour le heading, tu devras trouver toi-même la valeur qui convient le mieux à cette porte (0-360 sont les valeurs min/max), ou utiliser le bouton intégré du script pour la trouver.

    Pense à essayer différentes vitesses (comme une vitesse plus lente).

    <Note>
      Si une porte ne fonctionne pas du tout, il n'y a rien qui puisse être fait.
    </Note>
  </Accordion>

  <Accordion title="Les portes ne sont pas verrouillées après un redémarrage">
    Si une porte n'est pas verrouillée alors qu'elle devrait l'être après un redémarrage du script/serveur, cela signifie que tu as activé l'option de sauvegarde de l'état de verrouillage de la porte dans les paramètres du menu du script.
  </Accordion>

  <Accordion title="Je n'arrive pas à confirmer une nouvelle porte">
    Si tu n'arrives pas à confirmer une nouvelle porte avec la touche ENTRÉE, tu peux modifier les touches assignées dans le fichier `integrations/cl_integrations.lua`.
  </Accordion>
</AccordionGroup>
