---
title: "Servidor"
description: "Eventos y exports del lado servidor disponibles en Vehicles Keys."
icon: "server"
---

Esta página lista los eventos y exports del **lado servidor** disponibles en Vehicles Keys.

<CardGroup cols={2}>
  <Card title="Give keys to identifier" icon="key" href="/es/vehicles-keys/server/give-keys-to-identifier">
    Da llaves de vehículo a un jugador por identifier.
  </Card>

  <Card title="Give keys to player ID" icon="key" href="/es/vehicles-keys/server/give-keys-to-player-id">
    Da llaves de vehículo a un jugador conectado.
  </Card>

  <Card title="Remove keys from identifier" icon="key" href="/es/vehicles-keys/server/remove-keys-from-identifier">
    Elimina llaves de vehículo de un jugador por identifier.
  </Card>

  <Card title="Remove keys from player ID" icon="key" href="/es/vehicles-keys/server/remove-keys-from-player-id">
    Elimina llaves de vehículo de un jugador conectado.
  </Card>

  <Card title="Get identifier keys" icon="list" href="/es/vehicles-keys/server/get-identifier-keys">
    Obtén todas las llaves propiedad de un identifier.
  </Card>

  <Card title="Get player ID keys" icon="list" href="/es/vehicles-keys/server/get-player-id-keys">
    Obtén todas las llaves propiedad de un jugador conectado.
  </Card>

  <Card title="Get if player ID owns a plate" icon="circle-question" href="/es/vehicles-keys/server/get-if-player-id-owns-a-plate">
    Comprueba si un jugador es dueño de una placa.
  </Card>

  <Card title="Refresh player owned vehicles" icon="rotate" href="/es/vehicles-keys/server/refresh-player-owned-vehicles">
    Actualiza la lista de vehículos propios de un jugador.
  </Card>

  <Card title="Vehicle locked/unlocked" icon="lock" href="/es/vehicles-keys/server/vehicle-locked-unlocked">
    Se activa cuando cambia el estado de bloqueo de un vehículo.
  </Card>

  <Card title="Vehicle window broken" icon="car-burst" href="/es/vehicles-keys/server/vehicle-window-broken">
    Se activa cuando un jugador rompe la ventana de un vehículo.
  </Card>

  <Card title="Player hotwired a vehicle" icon="bolt" href="/es/vehicles-keys/server/player-hotwired-a-vehicle">
    Se activa cuando se puentea un vehículo.
  </Card>

  <Card title="Player lockpicked a vehicle" icon="lock-open" href="/es/vehicles-keys/server/player-lockpicked-a-vehicle">
    Se activa cuando se abre con ganzúa un vehículo.
  </Card>

  <Card title="Police alert" icon="siren-on" href="/es/vehicles-keys/server/police-alerted">
    Se activa una vez, del lado servidor, cuando se alerta a la policía.
  </Card>

  <Card title="Alarms" icon="bell" href="/es/vehicles-keys/server/alarms">
    Eventos para la activación de alarmas de vehículos.
  </Card>
</CardGroup>
