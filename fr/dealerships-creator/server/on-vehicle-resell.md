---
title: "À la revente d'un véhicule"
description: "Se déclenche côté serveur après qu'un joueur revend un véhicule à une concession."
icon: "hand-holding-dollar"
---

Cet event se déclenche après qu'un joueur revend un véhicule à une concession.

```lua Event
AddEventHandler("dealerships_creator:dealerships:onVehicleResell", function(dealershipId, plate, vehicleName, playerId, resellPrice)

end)
```

### Paramètres

| Nom           | Type de donnée | Description                                     |
| -------------- | --------- | ---------------------------------------------------- |
| `dealershipId` | integer   | L'ID de la concession où le véhicule a été revendu          |
| `plate`        | string    | La plaque du véhicule                                     |
| `vehicleName`  | string    | Le nom de spawn du véhicule                                  |
| `playerId`     | integer   | Server ID du joueur qui a revendu le véhicule                  |
| `resellPrice`  | integer   | Montant de l'argent reçu par le joueur                       |
