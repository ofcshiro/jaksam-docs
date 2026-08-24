---
title: "FAQ générale"
description: "Questions fréquentes communes à tous les scripts"
icon: "circle-user-circle-question"
---

Cette page contient les questions fréquentes communes à tous les scripts. Si ton problème n'est pas listé ici, vérifie la FAQ du script qui te pose problème.

<AccordionGroup>
  <Accordion title="Crash">
    Les crashs peuvent avoir 2 causes :

    - Tu dois whitelister ces modèles d'objets dans ton anticheat : `L1_1`, `GetHashKey('L1_1')`, `2116969379`
    - Si tu as toujours des crashs après avoir whitelisté ces modèles d'objets dans ton anticheat, consulte [cette page](/fr/jaksams-scripts/troubleshooting)

    _Si tu ne sais pas comment whitelister des modèles d'objets dans ton anticheat, demande au créateur de ton anticheat._
  </Accordion>

  <Accordion title="Attempted to index a nil value (field 'ESX')">
    Si tu as cette erreur, cela signifie que le script n'a pas pu récupérer le shared object d'ESX.

    Cette erreur peut être causée par d'autres erreurs dans ta console serveur/F8, qui se produisent avant celle-ci.

    Si tu n'as aucune autre erreur avant celle-ci, consulte [cette page](/fr/jaksams-scripts/troubleshooting).
  </Accordion>

  <Accordion title='Comment corriger l\'erreur "missing menu_default"'>
    Pour corriger l'erreur, lis simplement le tutoriel d'installation du script.
  </Accordion>

  <Accordion title="Les objets/props ne spawnent pas">
    Si les props ne spawnent pas, c'est très probablement un problème avec ton anticheat.

    Assure-toi de whitelister tous les props dans ton anticheat. Si tu ne sais pas comment faire, demande au créateur de ton anticheat.
  </Accordion>

  <Accordion title="Impossible de recevoir AUCUN item">
    Si tu as déjà essayé avec différents items et que tu n'arrives à en recevoir aucun, consulte [cette page](/fr/jaksams-scripts/troubleshooting).
  </Accordion>

  <Accordion title="Impossible de recevoir UNIQUEMENT LES ARMES">
    Si seules les armes posent problème mais que les items fonctionnent bien, voici les raisons possibles :

    - Sur ESX, c'est très probablement parce que ton serveur ne supporte pas la méthode standard d'ESX `xPlayer.addWeapon`
    - Sur QBCore, il se peut que ton inventaire modifie le comportement par défaut de `qb-inventory`

    Ce n'est pas un problème qui dépend du script, mais de ton framework/inventaire, et nous ne pouvons pas le résoudre — les méthodes standard doivent fonctionner.
  </Accordion>

  <Accordion title="Comment remplacer les notifications par défaut">
    Pour remplacer les notifications d'un script, consulte la documentation du script concerné. Il a des events qui permettent de désactiver la notification par défaut et d'en appeler une externe.

    _Note : l'intégration d'un script externe est entièrement de ta responsabilité._
  </Accordion>

  <Accordion title="Comment remplacer la barre de progression par défaut">
    Pour remplacer la barre de progression d'un script, consulte la documentation du script concerné. Il a des events qui permettent de désactiver la barre par défaut et d'en appeler une externe.

    _Note : l'intégration d'un script externe est entièrement de ta responsabilité._
  </Accordion>

  <Accordion title="Transferts de scripts">
    Les scripts ne peuvent être transférés qu'une seule fois via le FiveM Keymaster, en utilisant le bouton latéral au lieu de "Download". Il n'y a aucune révocation ni aucun transfert manuel, quelle que soit la situation.
  </Accordion>

  <Accordion title="Remboursements">
    Les achats sur la boutique de jaksam sont définitifs, ceci s'applique à toute situation — mauvais framework, mauvais comptes, etc. Nous ne pouvons donc malheureusement pas aider en cas de demande de remboursement.
  </Accordion>
</AccordionGroup>
