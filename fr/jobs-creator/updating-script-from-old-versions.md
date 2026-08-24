---
title: "Comment faire"
description: "Mises à jour de la base de données et du script étape par étape nécessaires lors de la mise à jour de Jobs Creator depuis une ancienne version."
icon: "clock-rotate-left"
tag: "Update"
---

Cette section explique comment mettre à jour le script depuis d'anciennes versions.

<Warning>
  Tu devras suivre **toutes les étapes** depuis ta _version actuelle_ jusqu'à la _plus récente_.
</Warning>

<Tip>
  Une **sauvegarde** est toujours conseillée avant de faire ces étapes.
</Tip>

<Tabs>
  <Tab title="3.5">
    Ajoute le code suivant dans `jobs_creator/integrations/sv_integrations.lua` et utilise la commande dans la console du serveur ou en jeu (il y aura un résultat affiché quand tu utilises la commande).

    ```lua
    RegisterCommand('updateRecipes', function(playerId)
        if(playerId == 0 or isAllowed(playerId)) then
            MySQL.Async.fetchAll('SELECT id, data FROM jobs_data WHERE type="crafting_table"', {}, function(results)
                for k, result in pairs(results) do
                    local markerId = result.id
    
                    if(result.data) then
                        local data = json.decode(result.data)
    
                        local newData = {}
    
                        local anythingChanged = false
    
                        if(data.craftablesItems) then
                            for itemName, craftingData in pairs(data.craftablesItems) do
                                if(not craftingData.recipes) then
                                    anythingChanged = true
                                end
    
                                newData[itemName] = {
                                    recipes = craftingData,
                                    animations = {}
                                }
                            end
                        end
    
                        local markerData = {
                            craftablesItems = newData
                        }
    
                        if(anythingChanged) then
                            print("Updating marker ID: " .. markerId)
                            MySQL.Async.execute("UPDATE jobs_data SET data=@newData WHERE id=@markerId", {
                                ['@newData'] = json.encode(markerData),
                                ['@markerId'] = markerId
                            })
                        else
                            print("Marker ID " .. markerId .. " doesn't need to update")
                        end
                    end
                end
            end)
        end
    end)
    ```
  </Tab>
  <Tab title="3.8">
    Exécute cette requête dans la base de données pour convertir les anciens items de la boutique de job.

    ```sql
    ALTER TABLE job_shop ADD COLUMN IF NOT EXISTS `item_type` VARCHAR(50) NOT NULL AFTER item_name;
    UPDATE job_shop SET item_type = "item_standard";
    ```
  </Tab>
  <Tab title="3.11">
    Ajoute le code suivant dans `jobs_creator/integrations/sv_integrations.lua` et utilise la commande dans la console du serveur ou en jeu (il y aura un résultat affiché quand tu utilises la commande).

    ```lua
    RegisterCommand('updateHarvest', function(playerId)
        if(playerId == 0 or isAllowed(playerId)) then
            MySQL.Async.fetchAll('SELECT id, data FROM jobs_data WHERE type="harvest"', {}, function(results)
                for k, result in pairs(results) do
                    local markerId = result.id
                    local data = json.decode(result.data)
    
                    local anythingChanged = false
    
                    if(data) then
                        if(data.itemQuantity) then
                            data.itemMinQuantity = data.itemQuantity
                            data.itemMaxQuantity = data.itemQuantity
                            data.itemQuantity = nil
    
                            anythingChanged = true
                        end
                    end
    
                    if(anythingChanged) then
                        print("Updating marker ID: " .. markerId)
                        MySQL.Async.execute("UPDATE jobs_data SET data=@newData WHERE id=@markerId", {
                            ['@newData'] = json.encode(data),
                            ['@markerId'] = markerId
                        })
                    else
                        print("Marker ID " .. markerId .. " doesn't need to update")
                    end
                end
            end)
        end
    end)
    ```
  </Tab>
  <Tab title="3.14">
    Exécute cette requête dans la base de données pour convertir les anciennes tables de la base de données et créer la nouvelle.

    ```sql
    CREATE TABLE IF NOT EXISTS `jobs_wardrobes` (
        `id` INT(11) NOT NULL AUTO_INCREMENT,
        `identifier` VARCHAR(100) NOT NULL COLLATE 'utf8mb4_general_ci',
        `label` VARCHAR(50) NOT NULL COLLATE 'utf8mb4_general_ci',
        `outfit` LONGTEXT NOT NULL DEFAULT '' COLLATE 'utf8mb4_bin',
        PRIMARY KEY (`id`) USING BTREE,
        INDEX `identifier` (`identifier`) USING BTREE
    );
    
    RENAME TABLE
        job_armory TO jobs_armories,
        job_garage TO jobs_garages,
        job_shop TO jobs_shops;
    ```
  </Tab>
  <Tab title="3.16">
    Ajoute le code suivant dans `jobs_creator/integrations/sv_integrations.lua` et utilise la commande dans la console du serveur ou en jeu (il y aura un résultat affiché quand tu utilises la commande).

    ```lua
    RegisterCommand('updateShops', function(playerId)
        if(playerId == 0 or isAllowed(playerId)) then
            MySQL.Async.fetchAll('SELECT id, data FROM jobs_data WHERE type="shop"', {}, function(results)
                for k, result in pairs(results) do
                    local markerId = result.id
                    local data = json.decode(result.data)
    
                    local anythingChanged = false
    
                    if(data and data.itemsOnSale) then
                        for itemName, itemData in pairs(data.itemsOnSale) do
                            if(type(itemData) == "number") then
                                data.itemsOnSale[itemName] = {
                                    price = itemData
                                }
    
                                anythingChanged = true
                            end
                        end
                    end
    
                    if(anythingChanged) then
                        print("Updating marker ID: " .. markerId)
                        MySQL.Async.execute("UPDATE jobs_data SET data=@newData WHERE id=@markerId", {
                            ['@newData'] = json.encode(data),
                            ['@markerId'] = markerId
                        })
                    else
                        print("Marker ID " .. markerId .. " doesn't need to update")
                    end
                end
            end)
        end
    end)
    ```
  </Tab>
  <Tab title="3.18">
    Ajoute le code suivant dans `jobs_creator/integrations/sv_integrations.lua` et utilise la commande dans la console du serveur ou en jeu (il y aura un résultat affiché quand tu utilises la commande).

    ```lua
    RegisterCommand('updateHarvest2', function(playerId)
        if(playerId == 0 or isAllowed(playerId)) then
            MySQL.Async.fetchAll('SELECT id, data FROM jobs_data WHERE type="harvest"', {}, function(results)
                for k, result in pairs(results) do
                    local markerId = result.id
                    local data = json.decode(result.data)
    
                    local anythingChanged = false
    
                    if(data) then
                        if(data.itemName or data.itemMinQuantity or data.itemMaxQuantity) then
    
                            data.harvestableItems = {
                                {
                                    name = data.itemName,
                                    minQuantity = data.itemMinQuantity,
                                    maxQuantity = data.itemMaxQuantity,
                                    time = data.itemTime,
                                    chances = 100
                                }
                            }
    
                            data.itemMinQuantity = nil
                            data.itemMaxQuantity = nil
                            data.itemTime = nil
                            data.itemName = nil
    
                            anythingChanged = true
                        end
                    end
    
                    if(anythingChanged) then
                        print("Updating marker ID: " .. markerId)
                        MySQL.Async.execute("UPDATE jobs_data SET data=@newData WHERE id=@markerId", {
                            ['@newData'] = json.encode(data),
                            ['@markerId'] = markerId
                        })
                    else
                        print("Marker ID " .. markerId .. " doesn't need to update")
                    end
                end
            end)
        end
    end)
    ```
  </Tab>
  <Tab title="4.0">
    <Note>
      Une fois le serveur lancé et le script démarré, exécute cette requête dans la base de données.
    </Note>

    ```sql
    UPDATE jobs_data SET grades_type="minimumGrade" WHERE grades_type IS NULL;
    ```

    Ajoute le code suivant dans `jobs_creator/integrations/sv_integrations.lua` et utilise **les deux commandes** dans la console du serveur ou en jeu (il y aura un résultat affiché quand tu utilises la commande).

    ```lua
    RegisterCommand('updateHarvest3', function(playerId)
        if(playerId == 0 or isAllowed(playerId)) then
            MySQL.Async.fetchAll('SELECT id, data FROM jobs_data WHERE type="harvest"', {}, function(results)
                for k, result in pairs(results) do
                    local markerId = result.id
                    local data = json.decode(result.data)
    
                    local anythingChanged = false
    
                    if(data) then
                        if(data.itemTool and not data.itemToolLoseProbability) then
                            data.itemToolLoseProbability = 100
                            anythingChanged = true
                        end
                    end
    
                    if(anythingChanged) then
                        print("Updating marker ID: " .. markerId)
                        MySQL.Async.execute("UPDATE jobs_data SET data=@newData WHERE id=@markerId", {
                            ['@newData'] = json.encode(data),
                            ['@markerId'] = markerId
                        })
                    else
                        print("Marker ID " .. markerId .. " doesn't need to update")
                    end
                end
            end)
        end
    end)
    
    RegisterCommand('updateMarkets', function(playerId)
        if(playerId == 0 or isAllowed(playerId)) then
            MySQL.Async.fetchAll('SELECT id, data FROM jobs_data WHERE type="market"', {}, function(results)
                for k, result in pairs(results) do
                    local markerId = result.id
                    local data = json.decode(result.data)
    
                    local anythingChanged = false
    
                    if(data and data.items) then
                        for itemName, itemData in pairs(data.items) do
                            if(itemData.price) then
                                itemData.maxPrice = itemData.price
                                itemData.minPrice = itemData.price
                                itemData.price = nil
    
                                anythingChanged = true
                            end
                        end
                    end
    
                    if(anythingChanged) then
                        print("Updating marker ID: " .. markerId)
                        MySQL.Async.execute("UPDATE jobs_data SET data=@newData WHERE id=@markerId", {
                            ['@newData'] = json.encode(data),
                            ['@markerId'] = markerId
                        })
                    else
                        print("Marker ID " .. markerId .. " doesn't need to update")
                    end
                end
            end)
        end
    end)
    ```
  </Tab>
  <Tab title="8.0">
    Ajoute le code suivant dans `jobs_creator/integrations/sv_integrations.lua`, sauvegarde et redémarre le script, et enfin utilise **la commande** dans la **console du serveur**.

    ```lua
    -- CONVERSION DE 7.11 vers 8.0
    RegisterCommand("upgrade_to_8", function(playerId)
        if(playerId ~= 0) then return end -- Uniquement pour la console du serveur
    
        local conversionCount = 0
    
        print("^3Converting to 8.0^7")
    
        local results = MySQL.Sync.fetchAll("SELECT * FROM jobs_data WHERE type='shop' OR type='market' OR type='harvest' OR type='process' OR type='crafting_table'")
    
        print("^3Automatically verifying " .. #results .. " markers^7")
    
        for i=1, #results do
            local currentMarker = results[i]
            local markerData = json.decode(currentMarker.data)
            local hasToUpdate = markerData and true or false
    
            if(currentMarker.type == "shop" and hasToUpdate) then
                local newItemsOnSale = {}
                markerData.itemsOnSale = markerData.itemsOnSale or {}
    
                if(#markerData.itemsOnSale == 0) then
                    for itemName, content in pairs(markerData.itemsOnSale) do
                        local object = { label = itemName, type = itemName:sub(1, #"WEAPON") == "WEAPON" and "weapon" or "item", metadata = nil, name = itemName }
                        content.object = object
    
                        table.insert(newItemsOnSale, content)
                    end
    
                    markerData.itemsOnSale = newItemsOnSale
                else
                    hasToUpdate = false -- Utilise déjà le tableau, donc déjà en 8.0
                end
            elseif(currentMarker.type == "market" and hasToUpdate) then
                local newItems = {}
                markerData.items = markerData.items or {}
    
                if(#markerData.items == 0) then
                    for itemName, content in pairs(markerData.items) do
                        local object = { label = itemName, type = itemName:sub(1, #"WEAPON") == "WEAPON" and "weapon" or "item", metadata = nil, name = itemName }
                        content.object = object
    
                        table.insert(newItems, content)
                    end
    
                    markerData.items = newItems
                else
                    hasToUpdate = false -- Utilise déjà le tableau, donc déjà en 8.0
                end
    
            elseif(currentMarker.type == "harvest" and hasToUpdate) then
                local newHarvestableItems = {}
                markerData.harvestableItems = markerData.harvestableItems or {}
    
                for i=1, #markerData.harvestableItems do
                    local harvestableItem = markerData.harvestableItems[i]
    
                    if(harvestableItem.name and hasToUpdate) then
                        local object = { label = harvestableItem.name, type = harvestableItem.name:sub(1, #"WEAPON") == "WEAPON" and "weapon" or "item", metadata = nil, name = harvestableItem.name }
    
                        harvestableItem.object = object
                        harvestableItem.name = nil
                        harvestableItem.itemTool = nil
    
                        table.insert(newHarvestableItems, harvestableItem)
                    else
                        hasToUpdate = false
                    end
                end
    
                if(hasToUpdate) then
                    if(markerData.itemTool) then
                        local toolObject = { label = markerData.itemTool, type = markerData.itemTool:sub(1, #"WEAPON") == "WEAPON" and "weapon" or "item", metadata = nil, name = markerData.itemTool }
                        markerData.itemTool = toolObject
                    end
                    markerData.harvestableItems = newHarvestableItems
                end
            elseif(currentMarker.type == "process" and hasToUpdate) then
                if(markerData.itemToAddName) then
                    local itemToAdd = { label = markerData.itemToAddName, type = markerData.itemToAddName:sub(1, #"WEAPON") == "WEAPON" and "weapon" or "item", metadata = nil, name = markerData.itemToAddName }
                    local itemToRemove = { label = markerData.itemToRemoveName, type = markerData.itemToRemoveName:sub(1, #"WEAPON") == "WEAPON" and "weapon" or "item", metadata = nil, name = markerData.itemToRemoveName }
    
                    markerData.itemToAddName = nil
                    markerData.itemToRemoveName = nil
    
                    markerData.itemToAdd = itemToAdd
                    markerData.itemToRemove = itemToRemove
                else
                    hasToUpdate = false
                end
            elseif(currentMarker.type == "crafting_table" and hasToUpdate) then
                local newCraftablesItems = {}
                markerData.craftablesItems = markerData.craftablesItems or {}
    
                if(#markerData.craftablesItems == 0) then
                    local foundAnything = false
                    for itemName, content in pairs(markerData.craftablesItems) do
                        local resultObject = { label = itemName, type = itemName:sub(1, #"WEAPON") == "WEAPON" and "weapon" or "item", metadata = nil, name = itemName }
                        content.resultObject = resultObject
    
                        local newRecipes = {}
                        for ingredientName, ingredientContent in pairs(content.recipes) do
                            local ingredientObject = { label = ingredientName, type = ingredientName:sub(1, #"WEAPON") == "WEAPON" and "weapon" or "item", metadata = nil, name = ingredientName }
                            ingredientContent.object = ingredientObject
    
                            table.insert(newRecipes, ingredientContent)
                        end
    
                        content.recipes = newRecipes
    
                        table.insert(newCraftablesItems, content)
    
                        foundAnything = true
                    end
    
                    if(foundAnything) then
                        markerData.craftablesItems = newCraftablesItems
                    else
                        hasToUpdate = false
                    end
                else
                    hasToUpdate = false -- Utilise déjà le tableau, donc déjà en 8.0
                end
            end
    
            if(hasToUpdate) then
                print("UPDATING MARKER ", currentMarker.id)
                currentMarker.data = json.encode(markerData)
    
                local affectedRows = MySQL.Sync.execute("UPDATE jobs_data SET data=@data WHERE id=@id", {
                    ["@data"] = currentMarker.data,
                    ["@id"] = currentMarker.id
                })
    
                if(affectedRows > 0) then
                    conversionCount = conversionCount + 1
                end
            end
        end
    
        if(conversionCount > 0) then
            print("^2Converted ^3" .. conversionCount .. "^2 markers successfully, restart the script!^7")
        else
            print("^3No markers to convert^7")
        end
    end)
    ```
  </Tab>
</Tabs>
