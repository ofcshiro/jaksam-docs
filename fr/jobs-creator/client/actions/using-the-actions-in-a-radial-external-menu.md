---
title: "Actions dans des menus externes"
description: "Déclenche les actions de Jobs Creator depuis n'importe quel menu externe ou radial via des events côté client."
icon: "circle-dot"
---

Tu peux utiliser les actions dans n'importe quel menu externe. Voici les déclencheurs que tu peux utiliser depuis des scripts externes.

<Warning>
  Assure-toi que le job a les actions activées dans les paramètres Jobs Creator de ce job pour éviter des problèmes. Tu peux activer les actions elles-mêmes tout en désactivant **"Can open actions menu"**.
</Warning>

## Vérifier l'identité

```lua
-- Déclencheur pour démarrer l'action de vérification d'identité
TriggerEvent("jobs_creator:actions:checkIdentity")
```

## Vérifier le propriétaire du véhicule

```lua
-- Déclencheur pour démarrer l'action de vérification du propriétaire du véhicule
TriggerEvent("jobs_creator:actions:checkVehicleOwner")
```

## Créer une facture

```lua
-- Déclencheur pour démarrer l'action de facturation
TriggerEvent("jobs_creator:actions:createBilling")
```

## Traîner un joueur

```lua
-- Déclencheur pour démarrer l'action de traîner
TriggerEvent("jobs_creator:actions:drag")
```

## Menotter un joueur

```lua
-- Déclencheur pour démarrer l'action de menottage souple
TriggerEvent("jobs_creator:actions:softHandcuff")
-- Déclencheur pour démarrer l'action de menottage strict
TriggerEvent("jobs_creator:actions:hardHandcuff")
```

## Soigner (gros soin)

```lua
-- Déclencheur pour démarrer l'action de gros soin
TriggerEvent("jobs_creator:actions:healBig")
```

## Soigner (petit soin)

```lua
-- Déclencheur pour démarrer l'action de petit soin
TriggerEvent("jobs_creator:actions:healSmall")
```

## Mise en fourrière

```lua
-- Déclencheur pour démarrer l'action de mise en fourrière
TriggerEvent("jobs_creator:actions:impoundVehicle")
```

## Menu des licences

```lua
-- Déclencheur pour afficher le menu des licences
TriggerEvent("jobs_creator:actions:checkLicenses")
```

## Crocheter une voiture

```lua
-- Déclencheur pour démarrer l'action de crochetage de voiture
TriggerEvent("jobs_creator:actions:lockpickCar")
```

## Mettre dans la voiture

```lua
-- Déclencheur pour démarrer l'action de mise dans la voiture
TriggerEvent("jobs_creator:actions:putInCar")
```

## Sortir de la voiture

```lua
-- Déclencheur pour démarrer l'action de sortie de la voiture
TriggerEvent("jobs_creator:actions:takeFromCar")
```

## Réparer le véhicule

```lua
-- Déclencheur pour démarrer l'action de réparation du véhicule
TriggerEvent("jobs_creator:actions:repairVehicle")
```

## Réanimer

```lua
-- Déclencheur pour démarrer l'action de réanimation
TriggerEvent("jobs_creator:actions:revive")
```

## Fouiller

```lua
-- Déclencheur pour démarrer l'action de fouille
TriggerEvent("jobs_creator:actions:search")
```

## Laver le véhicule

```lua
-- Déclencheur pour démarrer l'action de lavage du véhicule
TriggerEvent("jobs_creator:actions:washVehicle")
```

## Ouvrir le menu des objets à placer

```lua
-- Déclencheur pour ouvrir le menu des objets à placer
TriggerEvent("jobs_creator:actions:placeObject")
```
