---
title: "Weapon Stolen"
description: "Se dispara después de que un jugador roba algo desde el menú de acciones, solo si usas el registro/robo de jugadores por defecto, no funcionará si lo reemplazaste"
icon: "gun"
---

Se dispara después de que un jugador roba un arma desde el menú de acciones.

<Note>
  Esto solo funciona si usas la acción de registro/robo de jugadores por defecto — no se disparará si la reemplazaste por un módulo personalizado.
</Note>

<CodeGroup>

```lua Event
RegisterNetEvent("jobs_creator:actions:weaponStolen", function(playerId, targetId, weaponName)
end)
```

```lua Example
-- Este ejemplo para ESX "eliminará" las armas robadas (puede ser útil para policías)
RegisterNetEvent("jobs_creator:actions:weaponStolen", function(playerId, targetId, weaponName)
    local xPlayer = ESX.GetPlayerFromId(playerId)
    xPlayer.removeWeapon(weaponName)
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerId` | integer | La ID de servidor del jugador que robó el arma |
| `targetId` | integer | La ID de servidor de la víctima que perdió el arma |
| `weaponName` | string | Nombre del arma |
