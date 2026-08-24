---
title: "Territories"
description: "Zones basées sur des polygones qui peuvent être possédées et contestées par des gangs ou des jobs."
icon: "map"
---

Les territoires sont des zones basées sur des polygones qui peuvent être possédées et contestées par des gangs ou des jobs. La faction avec le plus de points au-dessus du seuil configuré devient propriétaire du territoire.

Les factions peuvent gagner des points via :

- Les **ventes de drogue** dans le territoire (toutes les méthodes de vente)
- Les **kills** (optionnel, configurable via le menu in-game)
- Des **scripts externes** via l'export [giveTerritoryPoints](/fr/drugs-creator/server/territories/give-territory-points)

La possession d'un territoire offre des avantages comme des prix de vente de drogue plus élevés, des chances réduites d'alerte police, et l'accès au système [Hired Dealers](/fr/drugs-creator/server/hired-dealers).

Le système supporte aussi les **hot zones** — des territoires sélectionnés aléatoirement qui reçoivent des multiplicateurs de bonus temporaires — et la **décroissance des points** sur des intervalles configurables.

Toute la configuration des territoires (zones, seuils, factions, hot zones, décroissance) se gère via le menu in-game `/drugscreator`.

<CardGroup cols={2}>
  <Card title="Give territory points" icon="arrow-up" href="/fr/drugs-creator/server/territories/give-territory-points">
    Ajoute des points à une faction dans un territoire.
  </Card>

  <Card title="Remove territory points" icon="arrow-down" href="/fr/drugs-creator/server/territories/remove-territory-points">
    Retire des points à une faction dans un territoire.
  </Card>

  <Card title="Reset territory points" icon="rotate-left" href="/fr/drugs-creator/server/territories/reset-territory-points">
    Remet à 0 les points d'une faction dans un territoire.
  </Card>

  <Card title="Ownership changed" icon="flag" href="/fr/drugs-creator/server/territories/ownership-changed">
    Se déclenche quand un territoire change de propriétaire.
  </Card>
</CardGroup>
