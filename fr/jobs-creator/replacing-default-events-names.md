---
title: "Remplacer les noms d'events par défaut"
description: "Renomme les noms d'events externes déclenchés par Jobs Creator, pour correspondre aux scripts de ton propre serveur."
icon: "pen"
hidden: true
---

# Remplacer les noms d'events par défaut

Si ton serveur utilise des noms d'events différents des noms par défaut, tu peux modifier ces noms dans `jobs_creator/integrations/cl_integrations.lua` **et** `jobs_creator/integrations/sv_integrations.lua`

Exemple de noms par défaut :

```lua
EXTERNAL_EVENTS_NAMES = {
    ["esx:getSharedObject"] = nil,
    
    ["esx_skin:save"] = "esx_skin:save",

    ["esx_billing:sendBill"] = "esx_billing:sendBill",

    ["jsfour-idcard:open"] = "jsfour-idcard:open",

    ["esx_license:removeLicense"] = "esx_license:removeLicense",
    ["esx_license:addLicense"] = "esx_license:addLicense",
}
```

<br />Exemple de noms modifiés :

```lua
EXTERNAL_EVENTS_NAMES = {
    ["esx:getSharedObject"] = "gamemode:getSharedObject",
    
    ["esx_skin:save"] = "my_skin_script:save",

    ["esx_billing:sendBill"] = "billing_ui:sendBill",

    ["jsfour-idcard:open"] = "jsfour-idcard:open",

    ["esx_license:removeLicense"] = "licenses:removeLicense",
    ["esx_license:addLicense"] = "licenses:addLicense",
}
```
