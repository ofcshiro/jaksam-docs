---
title: "Vehicle repaired"
description: "Se déclenche après qu'un véhicule est réparé via le menu d'actions du job, utile pour ajouter une logique de réparation supplémentaire."
icon: "wrench"
---

Se déclenche après qu'un véhicule est réparé avec le menu d'actions du job. Utile si tu veux ajouter une fonction de réparation supplémentaire aux fonctions actuelles.

```lua Event
AddEventHandler("jobs_creator:vehicleRepaired", function(vehicle)
    -- Tu peux ajouter les fonctions de réparation supplémentaires ici
end)
```

### Paramètres

| Nom | Type de donnée | Description |
| --- | --- | --- |
| `vehicle` | vehicle handle | Le handle du véhicule |
