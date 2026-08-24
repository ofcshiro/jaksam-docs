---
title: "Optimisation"
description: "Branche-toi sur les events d'items de ton inventaire pour améliorer les performances de Trackers Creator."
icon: "gauge-high"
---

Cette page te montre comment optimiser le script. Suivre toutes les instructions ci-dessous améliorera les performances du script.

## Vérification des items

Utilise ces events **côté serveur** juste après tout ajout/retrait d'item. Ils peuvent être utilisés n'importe où, tant que tu remplaces les paramètres par les bons.

```lua
TriggerEvent("framework:onItemAdded", playerId, itemName, itemCount)
```

```lua
TriggerEvent("framework:onItemRemoved", playerId, itemName, itemCount)
```

### Exemples

<Note>
  Si tu utilises quelque chose qui n'est pas listé dans les exemples, sa modification est à ta charge — les events listés ci-dessus fonctionnent partout s'ils sont utilisés correctement.
</Note>

#### ESX

<Info>
  ESX par défaut a déjà `esx:onAddInventoryItem` et `esx:onRemoveInventoryItem`, ce qui signifie que tu n'auras rien à ajouter. Suis l'exemple ci-dessous uniquement si tu n'as pas ces events pour une raison quelconque.
</Info>

Va dans `es_extended/server/classes/player.lua` et ajoute le code suivant :

<Frame>
  ![ESX item added/removed hook example 1](/images/immagine-2-1.png)
</Frame>

<Frame>
  ![ESX item added/removed hook example 2](/images/immagine-3.png)
</Frame>

#### OX Inventory (ESX)

Va dans `es_extended/server/classes/overrides/oxinventory.lua` et ajoute le code suivant :

<Frame>
  ![OX Inventory hook example 1](/images/immagine-4-1.png)
</Frame>

<Frame>
  ![OX Inventory hook example 2](/images/immagine.png)
</Frame>

#### QBCore (dernière version)

Va dans `qb-inventory/server/main.lua` et ajoute le code suivant :

<Frame>
  ![QBCore hook example 1](/images/immagine-5-1.png)
</Frame>

<Frame>
  ![QBCore hook example 2](/images/immagine-6.png)
</Frame>
