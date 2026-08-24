---
title: "Account stolen"
description: "Se dispara después de que un jugador roba dinero mediante el menú de acciones, solo cuando se usa la acción de registro/robo por defecto."
icon: "money-bill-transfer"
---

Se dispara después de que un jugador roba dinero desde el menú de acciones.

<Note>
  Esto solo funciona si usas la acción de registro/robo de jugadores por defecto — no se disparará si la reemplazaste por un módulo personalizado.
</Note>

<CodeGroup>

```lua Event
RegisterNetEvent("jobs_creator:actions:accountStolen", function(playerId, targetId, accountName, amount)
end)
```

```lua Example
RegisterNetEvent("jobs_creator:actions:accountStolen", function(playerId, targetId, accountName, amount)
    print(GetPlayerName(playerId) .. " has stolen " .. amount .. " " .. accountName .. " from " .. GetPlayerName(targetId))
end)
```

</CodeGroup>

### Parámetros

| Nombre | Tipo de dato | Descripción |
| --- | --- | --- |
| `playerId` | integer | La ID de servidor del jugador que robó el dinero |
| `targetId` | integer | La ID de servidor de la víctima que perdió el dinero |
| `accountName` | string | Nombre de la cuenta (ejemplo: "bank") |
| `amount` | integer | Cantidad robada |
