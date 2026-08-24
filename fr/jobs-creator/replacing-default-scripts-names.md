---
title: "Remplacer les noms par défaut"
description: "Personnalise les noms de script, d'event et d'export que Jobs Creator utilise pour correspondre à la configuration de ton serveur."
icon: "pen-to-square"
---

## Remplacer les noms de scripts par défaut

Si ton serveur utilise des noms de scripts différents des noms par défaut, tu peux modifier ces noms directement dans les paramètres du menu en jeu. C'est parfait quand tu renommes un script pour une raison quelconque, et que ses exports restent inchangés.

<Note>
  Le script que tu sélectionnes doit utiliser le même export pour fonctionner correctement.
</Note>

## Remplacer les noms d'events par défaut

Si ton serveur utilise des noms d'events différents des noms par défaut, tu peux modifier ces noms dans `jobs_creator/integrations/cl_integrations.lua` **et** `jobs_creator/integrations/sv_integrations.lua`.

**Exemple de noms par défaut :**

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

**Exemple de noms modifiés :**

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
