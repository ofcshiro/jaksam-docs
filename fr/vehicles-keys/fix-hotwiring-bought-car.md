---
title: "Corriger le court-circuitage d'un véhicule acheté"
description: "Actualise les véhicules possédés par un joueur après un achat afin qu'il n'ait pas besoin de le court-circuiter, pour les scripts de concession courants."
icon: "wrench"
---

## Script générique

Si tu dois court-circuiter un véhicule juste après l'avoir acheté, ajoute [cette simple ligne de code](/fr/vehicles-keys/client/refresh-self-owned-vehicles) à ton script, après que le véhicule a été ajouté à la table `owned_vehicles` / `player_vehicles` (selon le framework).

Tu voudras peut-être ajouter un `Citizen.Wait(2000)` avant cette ligne, au cas où le véhicule ne serait pas encore dans la table au moment où tu déclenches l'event.

## esx_vehicleshop

### Première étape

Va dans `esx_vehicleshop/server/main.lua` et recherche le code suivant :

<Frame>
  ![esx_vehicleshop setVehicleOwnedPlayerId before](/images/esx_vehicleshop_setVehicleOwnedPlayerId_before.png)
</Frame>

Et ajoute cette ligne :

```lua
exports["vehicles_keys"]:refreshPlayerOwnedVehicles(playerId)
```

<Frame>
  ![esx_vehicleshop setVehicleOwnedPlayerId after](/images/esx_vehicleshop_setVehicleOwnedPlayerId_after.png)
</Frame>

### Deuxième étape

Va dans `esx_vehicleshop/server/main.lua` (le même fichier que précédemment) et recherche le code suivant :

<Frame>
  ![esx_vehicleshop buyVehicle before](/images/esx_vehicleshop_buyVehicle_before.png)
</Frame>

Et ajoute cette ligne :

```lua
exports["vehicles_keys"]:refreshPlayerOwnedVehicles(source)
```

<Frame>
  ![esx_vehicleshop buyVehicle after](/images/esx_vehicleshop_buyVehicle_after.png)
</Frame>

## esx_advancedvehicleshop

Va dans `esx_advancedvehicleshop/server/main.lua` et recherche le code suivant :

<Frame>
  ![esx_advancedvehicleshop before](/images/esx_advancedvehicleshop_before.png)
</Frame>

Et ajoute cette ligne :

```lua
exports["vehicles_keys"]:refreshPlayerOwnedVehicles(source)
```

<Frame>
  ![esx_advancedvehicleshop after](/images/esx_advancedvehicleshop_after.png)
</Frame>

## qb-vehicleshop

### Première étape

Va dans `qb-vehicleshop/server.lua` et ajoute le code suivant après **tous** les appels à `exports.oxmysql:insert`.

<Note>
  Dans l'exemple, il n'est montré qu'une seule fois, mais tu dois l'ajouter plusieurs fois.
</Note>

<Frame>
  ![qb-vehicleshop before](/images/qb-vehicleshop_before.png)
</Frame>

Ajoute le code suivant :

```lua
SetTimeout(1000, function()
    exports["vehicles_keys"]:refreshPlayerOwnedVehicles( pData.PlayerData.source )
end)
```

Dans certains endroits, tu devras remplacer `pData` par autre chose. Voici où ajouter le code et de quoi dépend `pData`.

<Frame>
  ![qb-vehicleshop after](/images/qb-vehicleshop_after.png)
</Frame>

<Note>
  Les cercles verts affichés dans la capture d'écran doivent correspondre — donc si le premier est, par exemple, `targetPlayer`, le second doit aussi être `targetPlayer`.
</Note>

### Deuxième étape

Va dans `qb-vehicleshop/server.lua` (le même fichier que précédemment) et remplace tous ces events (ils se trouvent en bas du fichier) :

```lua
TriggerClientEvent('vehiclekeys:client:SetOwner', buyerId, plate)
```

par le code suivant :

```lua
exports["vehicles_keys"]:refreshPlayerOwnedVehicles(buyerId)
```

## okokVehicleShop

Va dans `okokVehicleShop/sv_utils.lua` et recherche le code suivant :

<Frame>
  ![okokVehicleShop before](/images/okokVehicleShop_before.png)
</Frame>

Et ajoute cette ligne :

```lua
exports["vehicles_keys"]:refreshPlayerOwnedVehicles(_source)
```

<Frame>
  ![okokVehicleShop after](/images/okokVehicleShop_after.png)
</Frame>

## s4-vehicleshop

Va dans `s4-vehicleshop/server.lua` et recherche le code suivant :

<Frame>
  ![s4-vehicleshop before](/images/s4-vehicleshop_before.png)
</Frame>

Et ajoute le code suivant :

```lua
SetTimeout(1000, function()
    exports["vehicles_keys"]:refreshPlayerOwnedVehicles(src)
end)
```

<Frame>
  ![s4-vehicleshop after](/images/s4-vehicleshop_after.png)
</Frame>

<Note>
  Ce code fonctionne aussi bien pour les versions _oxmysql_ que _ghmattimysql_.
</Note>

## t1ger_dealerships

### Première étape

Va dans `t1ger_dealerships/server/main.lua` et ajoute la ligne suivante en dessous de **toutes** les occurrences (il y en a plusieurs) du code montré dans l'exemple :

```lua
exports['t1ger_keys']:UpdateKeysToDatabase(props.plate, true)
```

<Frame>
  ![t1ger_dealerships before](/images/t1ger_dealerships_before.png)
</Frame>

Ajoute la ligne suivante :

```lua
exports["vehicles_keys"]:refreshPlayerOwnedVehicles(xPlayer.source)
```

<Frame>
  ![t1ger_dealerships after](/images/t1ger_dealerships_after.png)
</Frame>

### Deuxième étape

Va dans `t1ger_dealerships/server/main.lua` (le même fichier que précédemment) et recherche le code suivant :

<Frame>
  ![t1ger_dealerships2 before](/images/t1ger_dealerships2_before.png)
</Frame>

Ajoute la ligne suivante :

```lua
exports["vehicles_keys"]:refreshPlayerOwnedVehicles(xPlayer.source)
```

<Frame>
  ![t1ger_dealerships2 after](/images/t1ger_dealerships2_after.png)
</Frame>
