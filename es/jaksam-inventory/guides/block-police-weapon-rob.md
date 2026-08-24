---
title: "Evitar que Roben Armas Policiales"
icon: "user-shield"
description: "Restringe armas específicas para que solo los jugadores con el trabajo de policía puedan moverlas a su inventario"
---

¿Quieres asegurarte de que solo los oficiales de policía puedan mover armas policiales a su inventario? Esta guía te muestra cómo hacerlo, paso a paso.

Esta función evita que jugadores que no son policías muevan armas policiales a su inventario personal. Si un jugador intenta robar un arma policial, recibirá un mensaje de error y la transferencia será bloqueada.

<Note>
  Esta funcionalidad la proporciona automáticamente el hook `_hooks/sv_policeonly.lua` (por si quieres editarlo). Solo tienes que marcar tus armas como exclusivas para policía.
</Note>

## Guía paso a paso

<Steps>
  <Step title="Abre el archivo de ítems">
    Abre los archivos de tu servidor y navega hasta: `jaksam_inventory/_data/items.lua`
  </Step>
  <Step title="Busca o crea el arma">
    Busca el ítem de arma que quieres proteger (o créalo si no existe).
  </Step>
  <Step title="Márcala como exclusiva para policía">
    Agrega `policeOnly = true` a la definición del ítem.
  </Step>
  <Step title="Reinicia">
    Guarda el archivo y reinicia el script/recarga el servidor.
  </Step>
</Steps>

<Tip>
  ¡Eso es todo! Ahora solo los jugadores con el trabajo "police" podrán mover esa arma a su inventario personal.
</Tip>

## Ejemplos

### Ejemplo 1: Combat Pistol

```lua
['WEAPON_COMBATPISTOL'] = {
    label = 'Combat Pistol',
    weight = 1.0,
    stackable = false,
    close = true,
    description = 'A combat pistol',
    type = 'weapon',
    ammo = 'ammo_9mm',
    throwableOptions = {
        model = nil,
        coords = {x = 0.08, y = 0.03, z = -0.06},
        rot = {x = -25.45, y = -3.76, z = 49.99}
    },
    policeOnly = true  -- Solo la policía puede mover esta arma
},
```

### Ejemplo 2: Stun Gun

```lua
['WEAPON_STUNGUN'] = {
    label = 'Stun Gun',
    weight = 1.0,
    stackable = false,
    close = true,
    description = 'A police stun gun',
    type = 'weapon',
    policeOnly = true  -- Solo la policía puede mover esta arma
},
```

## Cómo funciona

El hook `sv_policeonly.lua` comprueba automáticamente cada vez que alguien intenta mover un arma con `policeOnly = true` a un inventario de jugador. Si el jugador no tiene el trabajo "police", la transferencia se bloquea y se le muestra un mensaje de error.

<Warning>
  Esto solo bloquea las transferencias hacia **inventarios de jugador**. Las armas policiales aún pueden moverse entre otros tipos de inventario (como storage, vehículos, etc.) por cualquier persona.
</Warning>
