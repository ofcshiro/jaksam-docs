---
title: "Client"
icon: "laptop"
description: "Exports côté client pour lire et contrôler l'inventaire"
tag: "Updated"
---

## Compatibilité

Ce script fonctionne avec d'autres systèmes d'inventaire populaires, comme es_extended, qb-inventory et ox_inventory.

<Info>
  Pour les fonctions ESX et QBCore, la configuration se fait automatiquement. Mais si tu veux continuer à utiliser les exports d'ox_inventory ou de qb-inventory pour la compatibilité, tu dois activer cette option dans le fichier : `jaksam_inventory/integrations/sv_integrations.lua`
</Info>

## Fonctions client

| Fonction | Description |
| --- | --- |
| [Get total item amount](/fr/jaksam-inventory/functions/client/get-total-item-amount) | Récupère la quantité totale d'un item spécifique dans l'inventaire du joueur |
| [Open inventory](/fr/jaksam-inventory/functions/client/open-inventory) | Ouvre un inventaire aux côtés de l'inventaire du joueur |
| [Close inventory](/fr/jaksam-inventory/functions/client/close-inventory) | Ferme l'interface de l'inventaire |
| [Get inventory](/fr/jaksam-inventory/functions/client/get-inventory) | Récupère l'inventaire personnel du joueur |
| [Get item by name](/fr/jaksam-inventory/functions/client/get-item-by-name) | Récupère le premier item trouvé dans l'inventaire personnel du joueur par nom |
| [Get items by name](/fr/jaksam-inventory/functions/client/get-items-by-name) | Récupère tous les items correspondant à un nom dans l'inventaire personnel du joueur |
| [Get item from slot](/fr/jaksam-inventory/functions/client/get-item-from-slot) | Récupère un item depuis un slot spécifique de l'inventaire du joueur |
| [Show hotbar](/fr/jaksam-inventory/functions/client/show-hotbar) | Affiche l'interface de la hotbar avec les 5 premiers slots |
| [Set hotbar disabled](/fr/jaksam-inventory/functions/client/set-hotbar-disabled) | Active ou désactive le fonctionnement de la hotbar |
| [Set hotkeys enabled](/fr/jaksam-inventory/functions/client/set-hotkeys-enabled) | Active ou désactive les hotkeys (slots 1-5) |
| [Are hotkeys enabled](/fr/jaksam-inventory/functions/client/are-hotkeys-enabled) | Renvoie si les hotkeys sont actuellement activés |
| [Dequip weapon](/fr/jaksam-inventory/functions/client/dequip-weapon) | Déséquipe l'arme actuellement équipée |
| [Set weapon wheel](/fr/jaksam-inventory/functions/client/set-weapon-wheel) | Active ou désactive la roue d'armes par défaut de GTA5 |
| [Set jaksam weapon wheel](/fr/jaksam-inventory/functions/client/set-jaksam-weapon-wheel) | Active ou désactive la roue d'armes radiale de jaksam |
| [Register action button](/fr/jaksam-inventory/functions/client/register-action-button) | Enregistre un bouton d'action personnalisé dans la barre d'outils de l'inventaire |
| [Unregister action button](/fr/jaksam-inventory/functions/client/unregister-action-button) | Supprime un bouton d'action précédemment enregistré |
| [Show action button](/fr/jaksam-inventory/functions/client/show-action-button) | Rend visible un bouton d'action caché |
| [Hide action button](/fr/jaksam-inventory/functions/client/hide-action-button) | Cache un bouton d'action sans le supprimer |
| [Get vehicle inventory limits](/fr/jaksam-inventory/functions/client/get-vehicle-inventory-limits) | Renvoie les limites du coffre/de la boîte à gants pour un véhicule |
| [Is inventory open](/fr/jaksam-inventory/functions/client/is-inventory-open) | Vérifie si un inventaire est actuellement ouvert |
| [Set inventory disabled](/fr/jaksam-inventory/functions/client/set-inventory-disabled) | Désactive ou réactive entièrement l'ouverture de l'inventaire |
| [Is inventory disabled](/fr/jaksam-inventory/functions/client/is-inventory-disabled) | Renvoie si l'ouverture de l'inventaire est actuellement désactivée |
