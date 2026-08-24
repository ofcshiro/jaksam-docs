---
title: "FAQ"
description: "Questions fréquentes spécifiques à Easy Allowlist & Queue."
icon: "circle-question"
---

Cette page contient des FAQ liées **uniquement à ce script** — assure-toi de consulter aussi la [FAQ générale](/fr/jaksams-scripts/common-faq) pour les autres problèmes.

<AccordionGroup>
  <Accordion title="Comment m'ajouter moi-même à l'allowlist">
    Le script détecte automatiquement si l'allowlist est complètement vide, tu seras donc automatiquement whitelisté la première fois que tu rejoins.

    Pour whitelister manuellement, envoie la demande d'allowlist à ton serveur puis utilise la commande `add_allowlist TonIdDeRequêteIci` dans la console du serveur.
  </Accordion>

  <Accordion title="Bloqué sur 'deferring connection...'">
    Si quand tu te connectes à ton serveur, Easy Allowlist affiche `deferring connection...` et reste bloqué sans aucune erreur, essaie ceci :

    <Steps>
      <Step title="Ouvre le fichier deferrals">
        Ouvre le fichier `easy_allowlist/server/deferrals.lua`.
      </Step>
      <Step title="Trouve le wait">
        Cherche le code `Citizen.Wait(500)`.
      </Step>
      <Step title="Augmente le wait">
        Modifie-le de `Citizen.Wait(500)` à `Citizen.Wait(10000)` ou plus si ça ne fonctionne toujours pas.
      </Step>
      <Step title="Sauvegarde et redémarre">
        Sauvegarde le fichier et redémarre le script.
      </Step>
    </Steps>
  </Accordion>
</AccordionGroup>
