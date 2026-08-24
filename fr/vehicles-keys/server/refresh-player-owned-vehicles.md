---
title: "Refresh player owned vehicles"
description: "Actualise la liste des véhicules possédés par un joueur côté serveur, par exemple après un achat."
icon: "rotate"
---

Utiliser cet export (côté serveur) actualisera la liste des véhicules possédés par le joueur (depuis `owned_vehicles` sur ESX ou `player_vehicles` sur QBCore).

```lua Export
exports["vehicles_keys"]:refreshPlayerOwnedVehicles(playerId, instantly)
```

### Paramètres

| Nom        | Type de donnée | Description                                                                                                                    |
| ----------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| `playerId`  | integer   | L'ID serveur du joueur                                                                                                                  |
| `instantly` | boolean   | Optionnel. Par défaut, il attend 2 secondes avant d'actualiser. Si tu es sûr d'en avoir besoin instantanément, passe `true`, sinon il peut être omis. |

### Exemple

```lua
RegisterNetEvent("vehicle_shop:playerBoughtVehicle", function(playerId, plate)
    -- Ceci actualisera les véhicules possédés par le joueur après qu'il ait acheté un véhicule (juste un exemple)

    exports["vehicles_keys"]:refreshPlayerOwnedVehicles(playerId)
end)
```
