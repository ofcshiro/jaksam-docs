---
title: "Refresh self owned vehicles"
description: "Actualise côté client la liste des véhicules possédés par le joueur local, par exemple après l'achat d'un nouveau véhicule."
icon: "rotate"
---

Déclencher cet event (depuis le côté client) actualisera la liste des véhicules possédés par le joueur (depuis `owned_vehicles` sur ESX ou `player_vehicles` sur QBCore).

Ceci est utile pour mettre à jour la liste des véhicules possédés lorsqu'un joueur achète un nouveau véhicule — tu peux ajouter cette ligne de code juste après un achat de véhicule réussi.

```lua Event
TriggerServerEvent("vehicles_keys:refreshMineOwnedVehicles")
```
