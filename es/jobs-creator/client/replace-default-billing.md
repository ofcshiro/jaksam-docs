---
title: "Replace default billing"
description: "Reemplaza el comportamiento por defecto del billing disparado desde el menú de acciones."
icon: "file-invoice-dollar"
---

Se dispara al usar la opción de billing en el menú de acciones F6.

<CodeGroup>

```lua Event
RegisterNetEvent("jobs_creator:actions:createBilling", function()
end)
```

```lua Example
-- Colocar en jobs_creator/integrations/cl_integrations.lua
RegisterNetEvent("jobs_creator:framework:ready", function()
    -- Desactiva el billing por defecto del script (de lo contrario habría 2 billings)
    exports["jobs_creator"]:disableScriptEvent("jobs_creator:actions:createBilling")
end)
RegisterNetEvent("jobs_creator:actions:createBilling", function()
    -- Usa el event de Billing UI
    TriggerEvent("billing_ui:activateBillingMode")
end)
```

</CodeGroup>

### ¿Dónde insertar el código?

Puedes colocarlo en el archivo `integrations/cl_integrations.lua` del script, **al final del archivo, en líneas nuevas**.
