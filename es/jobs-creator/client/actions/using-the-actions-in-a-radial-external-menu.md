---
title: "Actions in external menus"
description: "Dispara las acciones de Jobs Creator desde cualquier menú externo o radial usando events del lado del cliente."
icon: "circle-dot"
---

Puedes usar las acciones en cualquier menú externo. Aquí tienes los disparadores que puedes usar desde scripts externos.

<Warning>
  Asegúrate de que el job tenga las acciones habilitadas en los ajustes de Jobs Creator de ese job para evitar problemas. Puedes habilitar las propias acciones mientras desactivas **"Can open actions menu"**.
</Warning>

## Comprobar identidad

```lua
-- Disparador para iniciar la acción de comprobar identidad
TriggerEvent("jobs_creator:actions:checkIdentity")
```

## Comprobar propietario del vehículo

```lua
-- Disparador para iniciar la acción de comprobar el propietario del vehículo
TriggerEvent("jobs_creator:actions:checkVehicleOwner")
```

## Crear billing

```lua
-- Disparador para iniciar la acción de billing
TriggerEvent("jobs_creator:actions:createBilling")
```

## Arrastrar jugador

```lua
-- Disparador para iniciar la acción de arrastrar
TriggerEvent("jobs_creator:actions:drag")
```

## Esposar jugador

```lua
-- Disparador para iniciar la acción de esposado suave
TriggerEvent("jobs_creator:actions:softHandcuff")
-- Disparador para iniciar la acción de esposado fuerte
TriggerEvent("jobs_creator:actions:hardHandcuff")
```

## Curación grande

```lua
-- Disparador para iniciar la acción de curación grande
TriggerEvent("jobs_creator:actions:healBig")
```

## Curación pequeña

```lua
-- Disparador para iniciar la acción de curación pequeña
TriggerEvent("jobs_creator:actions:healSmall")
```

## Incautar

```lua
-- Disparador para iniciar la acción de incautación
TriggerEvent("jobs_creator:actions:impoundVehicle")
```

## Menú de licencias

```lua
-- Disparador para ver la acción del menú de licencias
TriggerEvent("jobs_creator:actions:checkLicenses")
```

## Forzar cerradura de vehículo

```lua
-- Disparador para iniciar la acción de forzar la cerradura del vehículo
TriggerEvent("jobs_creator:actions:lockpickCar")
```

## Meter en el vehículo

```lua
-- Disparador para iniciar la acción de meter en el vehículo
TriggerEvent("jobs_creator:actions:putInCar")
```

## Sacar del vehículo

```lua
-- Disparador para iniciar la acción de sacar del vehículo
TriggerEvent("jobs_creator:actions:takeFromCar")
```

## Reparar vehículo

```lua
-- Disparador para iniciar la acción de reparar vehículo
TriggerEvent("jobs_creator:actions:repairVehicle")
```

## Revivir

```lua
-- Disparador para iniciar la acción de revivir
TriggerEvent("jobs_creator:actions:revive")
```

## Buscar

```lua
-- Disparador para iniciar la acción de búsqueda
TriggerEvent("jobs_creator:actions:search")
```

## Lavar vehículo

```lua
-- Disparador para iniciar la acción de lavar vehículo
TriggerEvent("jobs_creator:actions:washVehicle")
```

## Abrir menú de objetos colocables

```lua
-- Disparador para abrir el menú de objetos colocables
TriggerEvent("jobs_creator:actions:placeObject")
```
