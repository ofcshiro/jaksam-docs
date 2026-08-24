---
title: "Get if player is owner of vehicle plate"
description: "Vérifie si un joueur donné est propriétaire d'une plaque de véhicule donnée."
icon: "drivers-license"
---

Renvoie si un joueur (ID) est propriétaire d'une plaque donnée.

<CodeGroup>

```lua Export
exports["jobs_creator"]:isPlayerOwnerOfVehiclePlate(playerId, plate)
```

```lua Example
local playerId = 1
local plate = "40PQB261"
local isTheVehicleOwner = exports["jobs_creator"]:isPlayerOwnerOfVehiclePlate(playerId, plate)
print("Is the player owner of that plate: " .. tostring(isTheVehicleOwner))
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | integer | ID serveur du joueur |
| `plate` | string | Plaque du véhicule |

### Valeur de retour

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `isOwner` | boolean | Indique si le joueur est propriétaire du véhicule ou non |
