---
title: "Comandos"
icon: "slash-forward"
description: "Lista completa de comandos de admin para gestionar ítems, inventarios y stashes"
---

# Comandos de Admin

<Note>
  Todos los comandos de admin requieren **permiso ACE**. Usa `/inventory` para comprobar si lo tienes.
</Note>

## `/inventory`

Abre el menú de admin para gestionar ítems, tiendas, stashes, ver estadísticas, etc.

## `/giveitem`

Entrega ítems a un jugador o inventario.

<ParamField path="inventoryId|playerId|'me'" type="string" required>
  Inventario objetivo, ID del jugador, o `me` para ti mismo
</ParamField>

<ParamField path="itemName" type="string" required>
  Nombre del ítem a entregar
</ParamField>

<ParamField path="amount" type="number" required>
  Cantidad a entregar
</ParamField>

<ParamField path="slotId" type="number">
  Slot específico opcional donde colocar el ítem
</ParamField>

```bash
/giveitem me bread 10                     # Entrega 10 bread a ti mismo
/giveitem 1 water 5                       # Entrega 5 water al jugador 1
/giveitem stash_police weapon_pistol 1 3  # Entrega 1 weapon_pistol a stash_police en el slot 3
```

## `/removeitem`

Elimina ítems de un jugador o inventario.

<ParamField path="inventoryId" type="string" required>
  Inventario objetivo o ID del jugador
</ParamField>

<ParamField path="itemName" type="string" required>
  Nombre del ítem a eliminar
</ParamField>

<ParamField path="amount" type="number" required>
  Cantidad a eliminar
</ParamField>

<ParamField path="slotId" type="number">
  Slot específico opcional del cual eliminar
</ParamField>

```bash
/removeitem 1 bread 10                    # Elimina 10 bread del inventario del jugador 1
/removeitem stash_police weapon_pistol 1  # Elimina 1 weapon_pistol de stash_police
```

## `/clearinventory`

Elimina todos los ítems de un inventario. Si `inventoryId` está vacío, limpia tu propio inventario. También puedes excluir un ítem para que no se elimine.

<ParamField path="inventoryId" type="string">
  Inventario objetivo. Por defecto es tu propio inventario si se omite
</ParamField>

<ParamField path="excludedItemName" type="string">
  Ítem a conservar, excluido de la limpieza
</ParamField>

```bash
/clearinventory          # Limpia tu inventario
/clearinventory 1        # Limpia el inventario del jugador 1
/clearinventory 2 phone  # Limpia el inventario del jugador 2 pero conserva phone
```

## `/openinventory`

Abre el inventario de otro jugador.

<ParamField path="targetPlayerId" type="number" required>
  ID del jugador cuyo inventario se va a abrir
</ParamField>

```bash
/openinventory 1  # Abre el inventario del jugador 1
```

## `/saveinventories`

Fuerza el guardado de todos los inventarios modificados en la base de datos.

<CardGroup cols={2}>
  <Card title="Gestión de Inventario" icon="box-open">
    `/inventory`, `/giveitem`, `/removeitem`, `/clearinventory`
  </Card>

  <Card title="Acciones de Jugador" icon="user">
    `/openinventory`, `/saveinventories`
  </Card>
</CardGroup>
