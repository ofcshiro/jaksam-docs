---
title: "Optimización"
description: "Engánchate a los events de items de tu inventario para mejorar el rendimiento de Trackers Creator."
icon: "gauge-high"
---

Esta página te muestra cómo optimizar el script. Seguir todas las instrucciones de abajo mejorará el rendimiento del script.

## Comprobación de items

Usa estos events del **lado del servidor** justo después de cualquier adición/eliminación de items. Se pueden usar en cualquier lugar, siempre que reemplaces los parámetros por los adecuados.

```lua
TriggerEvent("framework:onItemAdded", playerId, itemName, itemCount)
```

```lua
TriggerEvent("framework:onItemRemoved", playerId, itemName, itemCount)
```

### Ejemplos

<Note>
  Si usas algo que no está en los ejemplos, adaptarlo depende de ti — los events indicados arriba funcionan en cualquier lugar si se usan correctamente.
</Note>

#### ESX

<Info>
  El ESX predeterminado ya tiene `esx:onAddInventoryItem` y `esx:onRemoveInventoryItem`, por lo que no necesitarás añadir nada. Sigue el ejemplo de abajo solo si no tienes esos events por algún motivo.
</Info>

Ve a `es_extended/server/classes/player.lua` y añade el siguiente código:

<Frame>
  ![ESX item added/removed hook example 1](/images/immagine-2-1.png)
</Frame>

<Frame>
  ![ESX item added/removed hook example 2](/images/immagine-3.png)
</Frame>

#### OX Inventory (ESX)

Ve a `es_extended/server/classes/overrides/oxinventory.lua` y añade el siguiente código:

<Frame>
  ![OX Inventory hook example 1](/images/immagine-4-1.png)
</Frame>

<Frame>
  ![OX Inventory hook example 2](/images/immagine.png)
</Frame>

#### QBCore (última versión)

Ve a `qb-inventory/server/main.lua` y añade el siguiente código:

<Frame>
  ![QBCore hook example 1](/images/immagine-5-1.png)
</Frame>

<Frame>
  ![QBCore hook example 2](/images/immagine-6.png)
</Frame>
