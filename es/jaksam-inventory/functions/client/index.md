---
title: "Client"
icon: "laptop"
description: "Exports del lado del cliente para leer y controlar el inventario"
tag: "Updated"
---

## Compatibilidad

Este script funciona con otros sistemas de inventario populares, como es_extended, qb-inventory y ox_inventory.

<Info>
  Para las funciones de ESX y QBCore, la configuración se realiza automáticamente. Pero, si quieres seguir usando los exports de ox_inventory o qb-inventory por compatibilidad, debes activar esta opción en el archivo: `jaksam_inventory/integrations/sv_integrations.lua`
</Info>

## Funciones de cliente

| Función | Descripción |
| --- | --- |
| [Get total item amount](/es/jaksam-inventory/functions/client/get-total-item-amount) | Obtiene la cantidad total de un ítem específico en el inventario del jugador |
| [Open inventory](/es/jaksam-inventory/functions/client/open-inventory) | Abre un inventario junto al inventario del jugador |
| [Close inventory](/es/jaksam-inventory/functions/client/close-inventory) | Cierra la interfaz del inventario |
| [Get inventory](/es/jaksam-inventory/functions/client/get-inventory) | Obtiene el inventario propio del jugador |
| [Get item by name](/es/jaksam-inventory/functions/client/get-item-by-name) | Obtiene el primer ítem encontrado en el inventario propio del jugador por nombre |
| [Get items by name](/es/jaksam-inventory/functions/client/get-items-by-name) | Obtiene todos los ítems que coinciden con un nombre en el inventario propio del jugador |
| [Get item from slot](/es/jaksam-inventory/functions/client/get-item-from-slot) | Obtiene un ítem de un slot específico en el inventario del jugador |
| [Show hotbar](/es/jaksam-inventory/functions/client/show-hotbar) | Muestra la interfaz de la hotbar con los primeros 5 slots |
| [Set hotbar disabled](/es/jaksam-inventory/functions/client/set-hotbar-disabled) | Habilita o deshabilita la funcionalidad de la hotbar |
| [Set hotkeys enabled](/es/jaksam-inventory/functions/client/set-hotkeys-enabled) | Habilita o deshabilita los hotkeys (slots 1-5) |
| [Are hotkeys enabled](/es/jaksam-inventory/functions/client/are-hotkeys-enabled) | Devuelve si los hotkeys están actualmente habilitados |
| [Dequip weapon](/es/jaksam-inventory/functions/client/dequip-weapon) | Desequipa el arma actualmente equipada |
| [Set weapon wheel](/es/jaksam-inventory/functions/client/set-weapon-wheel) | Habilita o deshabilita la rueda de armas predeterminada de GTA5 |
| [Set jaksam weapon wheel](/es/jaksam-inventory/functions/client/set-jaksam-weapon-wheel) | Habilita o deshabilita la rueda de armas radial de jaksam |
| [Register action button](/es/jaksam-inventory/functions/client/register-action-button) | Registra un botón de acción personalizado en la barra de herramientas del inventario |
| [Unregister action button](/es/jaksam-inventory/functions/client/unregister-action-button) | Elimina un botón de acción previamente registrado |
| [Show action button](/es/jaksam-inventory/functions/client/show-action-button) | Hace visible un botón de acción oculto |
| [Hide action button](/es/jaksam-inventory/functions/client/hide-action-button) | Oculta un botón de acción sin eliminarlo |
| [Get vehicle inventory limits](/es/jaksam-inventory/functions/client/get-vehicle-inventory-limits) | Devuelve los límites del maletero/guantera de un vehículo |
| [Is inventory open](/es/jaksam-inventory/functions/client/is-inventory-open) | Comprueba si un inventario está actualmente abierto |
| [Set inventory disabled](/es/jaksam-inventory/functions/client/set-inventory-disabled) | Deshabilita o rehabilita por completo la apertura del inventario |
| [Is inventory disabled](/es/jaksam-inventory/functions/client/is-inventory-disabled) | Devuelve si la apertura del inventario está actualmente deshabilitada |
