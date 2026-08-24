---
title: "Replace default billing"
description: "Remplace le comportement de facturation par défaut déclenché depuis le menu d'actions."
icon: "file-invoice-dollar"
---

Se déclenche en utilisant l'option de facturation dans le menu d'actions F6.

<CodeGroup>

```lua Event
RegisterNetEvent("jobs_creator:actions:createBilling", function()
end)
```

```lua Example
-- To place in jobs_creator/integrations/cl_integrations.lua
RegisterNetEvent("jobs_creator:framework:ready", function()
    -- Disables the default script billing (otherwise there would be 2 billings)
    exports["jobs_creator"]:disableScriptEvent("jobs_creator:actions:createBilling")
end)
RegisterNetEvent("jobs_creator:actions:createBilling", function()
    -- Uses Billing UI event
    TriggerEvent("billing_ui:activateBillingMode")
end)
```

</CodeGroup>

### Où insérer le code ?

Tu peux le placer dans le fichier `integrations/cl_integrations.lua` du script, **en bas du fichier sur de nouvelles lignes**.
