---
title: "Territorios"
description: "Zonas basadas en polígonos que pueden ser poseídas y disputadas por gangs o jobs."
icon: "map"
---

Los territorios son zonas basadas en polígonos que pueden ser poseídas y disputadas por gangs o jobs. La facción con más puntos por encima del umbral configurado se convierte en la propietaria del territorio.

Las facciones pueden ganar puntos mediante:

- **Ventas de drogas** dentro del territorio (todos los métodos de venta)
- **Kills** (opcional, configurable a través del menú ingame)
- **Scripts externos** mediante el export [giveTerritoryPoints](/es/drugs-creator/server/territories/give-territory-points)

Poseer un territorio ofrece beneficios como precios de venta de drogas más altos, menor probabilidad de alerta policial, y acceso al sistema de [Hired Dealers](/es/drugs-creator/server/hired-dealers).

El sistema también admite **hot zones** — territorios elegidos al azar que reciben multiplicadores de bonificación temporales — y **decaimiento de puntos** en intervalos configurables.

Toda la configuración de territorios (zonas, umbrales, facciones, hot zones, decaimiento) se gestiona a través del menú ingame `/drugscreator`.

<CardGroup cols={2}>
  <Card title="Give territory points" icon="arrow-up" href="/es/drugs-creator/server/territories/give-territory-points">
    Añade puntos a una facción en un territorio.
  </Card>

  <Card title="Remove territory points" icon="arrow-down" href="/es/drugs-creator/server/territories/remove-territory-points">
    Quita puntos a una facción en un territorio.
  </Card>

  <Card title="Reset territory points" icon="rotate-left" href="/es/drugs-creator/server/territories/reset-territory-points">
    Reinicia a 0 los puntos de una facción en un territorio.
  </Card>

  <Card title="Ownership changed" icon="flag" href="/es/drugs-creator/server/territories/ownership-changed">
    Se activa cuando un territorio cambia de propietario.
  </Card>
</CardGroup>
