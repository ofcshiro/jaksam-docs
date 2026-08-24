---
title: "Recetas de Crafting (Arrastrar y Soltar)"
icon: "flask-gear"
description: "Permite a los jugadores craftear ítems arrastrando un ítem sobre otro usando el hook de crafting integrado"
---

¿Quieres que los jugadores craftéen ítems arrastrando un ítem sobre otro? Esta guía te muestra cómo hacerlo, paso a paso.

Esta función permite a los jugadores craftear ítems arrastrando un **ítem origen** sobre un **ítem destino** dentro del mismo inventario. Cuando la receta coincide, los ítems se combinan y se crea el resultado.

<Note>
  Esta funcionalidad la proporciona el hook `_hooks/sv_craftings.lua`. Solo tienes que agregar tus recetas a la tabla `CRAFTING_RECIPES`.
</Note>

## Cómo funciona

<Steps>
  <Step title="Arrastra el origen sobre el destino">
    El jugador arrastra un **ítem origen** sobre un **ítem destino** dentro del mismo inventario.
  </Step>
  <Step title="Comprobación de la receta">
    El sistema comprueba si existe una receta que coincida.
  </Step>
  <Step title="Se realiza el crafting">
    Si la receta coincide y las cantidades son suficientes, el crafting se realiza.
  </Step>
  <Step title="Se consumen los ítems">
    Se eliminan el ítem origen y/o el ítem destino (según la configuración de la receta).
  </Step>
  <Step title="Se agrega el resultado">
    El ítem resultante se agrega al inventario.
  </Step>
</Steps>

## Guía paso a paso

<Steps>
  <Step title="Abre el hook de crafting">
    Navega hasta: `jaksam_inventory/_hooks/sv_craftings.lua`
  </Step>
  <Step title="Busca la tabla de recetas">
    Busca la tabla `CRAFTING_RECIPES` (está cerca del inicio del archivo).
  </Step>
  <Step title="Agrega tu receta">
    Agrega tu receta siguiendo este formato:

    ```lua
        local CRAFTING_RECIPES = {
            ["source_item_name"] = {
                sourceQuantityRequired = 1,        -- Cuántos ítems origen se necesitan
                sourceIsToRemove = true,           -- ¿Eliminar el ítem origen después del crafting?
                targetItem = "target_item_name",  -- Nombre del ítem destino
                targetQuantity = 1,                -- Cuántos ítems destino se necesitan
                targetIsToRemove = true,           -- ¿Eliminar el ítem destino después del crafting?
                resultItem = "result_item_name",  -- Nombre del ítem creado
                resultQuantity = 1,                -- Cuántos ítems resultantes se crean
            },
        }
    ```
  </Step>
  <Step title="Reinicia">
    Guarda el archivo y reinicia el script/recarga el servidor.
  </Step>
</Steps>

<Tip>
  ¡Eso es todo! Ahora los jugadores pueden arrastrar el ítem origen sobre el ítem destino para craftear.
</Tip>

## Explicación de las propiedades de la receta

<ParamField path="sourceQuantityRequired" type="number">
  Cuántas unidades del ítem origen se necesitan para la receta
</ParamField>

<ParamField path="sourceIsToRemove" type="boolean">
  Configúralo en `true` si el ítem origen debe eliminarse después del crafting, `false` para conservarlo
</ParamField>

<ParamField path="targetItem" type="string">
  El nombre exacto (tal como está definido en `items.lua`) del ítem sobre el que arrastras el ítem origen
</ParamField>

<ParamField path="targetQuantity" type="number">
  Cuántas unidades del ítem destino se necesitan para la receta
</ParamField>

<ParamField path="targetIsToRemove" type="boolean">
  Configúralo en `true` si el ítem destino debe eliminarse después del crafting, `false` para conservarlo
</ParamField>

<ParamField path="resultItem" type="string">
  El nombre exacto (tal como está definido en `items.lua`) del ítem que se creará
</ParamField>

<ParamField path="resultQuantity" type="number">
  Cuántos ítems resultantes se crearán
</ParamField>

## Ejemplos

<Tabs>
  <Tab title="Mejorar mira a térmica">
    Combina una llave inglesa con una mira avanzada para crear una mira térmica:

    ```lua
        ["weapon_wrench"] = {
            sourceQuantityRequired = 1,
            sourceIsToRemove = false,              -- Conserva la llave inglesa (herramienta reutilizable)
            targetItem = "advanced_scope",
            targetQuantity = 1,
            targetIsToRemove = true,               -- Elimina la mira avanzada
            resultItem = "thermal_scope",
            resultQuantity = 1,
        },
    ```

    **Cómo usarlo:** Arrastra la llave inglesa sobre la mira avanzada → se crea la mira térmica, la llave inglesa se conserva, la mira avanzada se elimina.
  </Tab>
  <Tab title="Combinar materiales">
    Combina 2 piezas de madera con 1 clavo para crear una tabla de madera:

    ```lua
        ["wood"] = {
            sourceQuantityRequired = 2,
            sourceIsToRemove = true,               -- Elimina las 2 piezas de madera
            targetItem = "nail",
            targetQuantity = 1,
            targetIsToRemove = true,               -- Elimina el clavo
            resultItem = "wooden_plank",
            resultQuantity = 1,
        },
    ```

    **Cómo usarlo:** Arrastra 2 ítems de madera sobre 1 clavo → se crea la tabla de madera, ambos materiales se consumen.
  </Tab>
</Tabs>

## Notas importantes

<CardGroup cols={2}>
  <Card title="Solo el mismo inventario" icon="box">
    El crafting solo funciona cuando ambos ítems están en el **mismo inventario** (no puedes arrastrar desde el inventario del jugador al inventario del vehículo)
  </Card>

  <Card title="Los nombres de los ítems deben coincidir" icon="fingerprint">
    Los nombres de `targetItem` y `resultItem` deben coincidir exactamente con los nombres de los ítems en `_data/items.lua`
  </Card>

  <Card title="Comprobación de cantidad" icon="calculator">
    El sistema comprueba automáticamente si tienes suficientes ítems antes de craftear
  </Card>

  <Card title="Múltiples recetas" icon="layer-group">
    Puedes agregar tantas recetas como quieras a la tabla `CRAFTING_RECIPES`
  </Card>
</CardGroup>

<Warning>
  **Un origen, múltiples destinos:** Cada ítem origen solo puede tener una receta. Si necesitas múltiples recetas para el mismo ítem origen, tendrás que usar ítems origen diferentes o crear sistemas de crafting independientes.
</Warning>
