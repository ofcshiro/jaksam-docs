---
title: "Item Stolen"
description: "Se déclenche après qu'un joueur vole quelque chose depuis le menu d'actions, uniquement si tu utilises la fouille/vol de joueur par défaut, ça ne fonctionnera pas si tu l'as remplacée"
icon: "hand"
---

Se déclenche après qu'un joueur vole quelque chose depuis le menu d'actions.

<Note>
  Ceci ne fonctionne que si tu utilises l'action fouille/vol de joueur par défaut — ça ne se déclenchera pas si tu l'as remplacée par un module personnalisé.
</Note>

<CodeGroup>

```lua Event
RegisterNetEvent("jobs_creator:actions:itemStolen", function(playerId, targetId, itemName, itemQuantity)
end)
```

```lua Example
-- Cet exemple pour ESX va "supprimer" tous les items volés
RegisterNetEvent("jobs_creator:actions:itemStolen", function(playerId, targetId, itemName, itemQuantity)
    local xPlayer = ESX.GetPlayerFromId(playerId)
    xPlayer.removeInventoryItem(itemName, itemQuantity)
end)
```

</CodeGroup>

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `playerId` | integer | Le server ID du joueur qui a volé l'item |
| `targetId` | integer | Le server ID de la victime qui a perdu l'item |
| `itemName` | string | Nom de l'item |
| `itemQuantity` | integer | Quantité volée |
