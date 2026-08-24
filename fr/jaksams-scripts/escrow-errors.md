---
title: "Erreurs Escrow"
description: "Solutions aux erreurs courantes causées par le système d'escrow des assets FiveM"
icon: "lock-hashtag"
---

<Danger>
  Si les scripts fonctionnent et qu'ils cessent de fonctionner après quelques redémarrages du serveur, tu as un virus sur ton serveur. Nous ne pouvons pas t'aider dans ce cas.
</Danger>

Tu trouveras ici les solutions aux erreurs courantes lors de l'utilisation des scripts de jaksam, dues au système d'Escrow de FiveM.

Pour vérifier si ton erreur est causée par l'escrow des assets FiveM, redémarre simplement le script et vérifie **à la fois** la **console F8** et la **console serveur** (txAdmin) à la recherche d'erreurs.

## Comment savoir si mon erreur est causée par le système d'escrow de FiveM ?

Pour comprendre si quelque chose dans un script ne fonctionne pas à cause du système d'escrow des assets FiveM, procède ainsi :

<Steps>
  <Step title="Redémarre le script">
    Redémarre le script qui pose problème, en utilisant la commande `ensure nom_de_ton_script` dans la console txAdmin, ou en le redémarrant comme tu le fais habituellement.

    <Frame caption="exemple de redémarrage via F8 en jeu">
      ![in-game F8 restart example](/images/f8_restart.gif)
    </Frame>

    <Frame caption="exemple de redémarrage via la console serveur">
      ![server console restart example](/images/server_restart.gif)
    </Frame>
  </Step>
  <Step title="Vérifie les deux consoles">
    Vérifie **à la fois** la console txAdmin (console serveur) **et** la console F8 en jeu, à la recherche d'erreurs.
  </Step>
  <Step title="Compare avec les erreurs connues">
    S'il y a une erreur similaire à celles des exemples ci-dessous, ton problème **est causé par le système d'escrow des assets FiveM**.
  </Step>
</Steps>

### Exemples d'erreurs causées par le système d'escrow de FiveM

<Frame caption="Solution : voir Error parsing script ci-dessous">
  ![Escrow error example](/images/error_parsing.png)
</Frame>

<Frame caption="Solution : voir Error parsing script ci-dessous">
  ![Escrow error example](/images/error_parsing_2.png)
</Frame>

<Frame caption="Solution : voir Failed to verify protected resource ci-dessous">
  ![Escrow error example](/images/failed_to_verify_protected_resource.png)
</Frame>

<Frame caption="Solution : voir You lack the required entitlement ci-dessous">
  ![Escrow error example](/images/lack_entitlement.jpg)
</Frame>

## Causes courantes

Voici les causes les plus fréquentes pour **toutes** les erreurs d'escrow ci-dessous — vérifie-les en premier avant de passer aux sections spécifiques à chaque erreur :

- Tu transfères le fichier du script un par un vers ton VPS, au lieu d'uploader le **.zip** et de l'extraire **après** qu'il soit déjà sur le VPS
- Tu utilises **FileZilla** (ou ton hébergeur l'utilise) — utilise [WinSCP](https://winscp.net/eng/download.php) à la place
- Le téléchargement était corrompu — essaie une installation propre et neuve
- Tu as un virus sur ton serveur qui modifie les fichiers de script (très probable si rien d'autre ne résout le problème)

Autres prérequis généraux :

- Version **minimum** des server artifacts : 4752
- OneSync doit être activé
- Utilise la bonne clé de licence, générée par le même compte que celui utilisé pour télécharger le script

<Tip>
  Il est **fortement** recommandé de lire attentivement toutes les sections ci-dessous, car ces solutions sont testées par de nombreux utilisateurs et sont censées fonctionner. Si aucune ne fonctionne, consulte [Que faire si rien ne résout les erreurs](#que-faire-si-rien-ne-resout-les-erreurs).
</Tip>

Tu peux trouver tous les scripts de jaksam [ici](https://jaksam1074-fivem-scripts.tebex.io/).

<AccordionGroup>
  <Accordion title="Error parsing script ... <\1>">
    **Exemple** de message d'erreur :

    ```text
    Error parsing script @jobs_creator/server/markers/job_shop.lua in resource jobs_creator: @jobs_creator/server/markers/job_shop.lua:1: syntax error near '<\1>'
    ```

    ### Raisons possibles

    En plus des [causes courantes](#causes-courantes) ci-dessus, cette erreur peut aussi se produire si :

    - Tu dois peut-être vider les caches du **serveur**

    ### Comment vérifier ma version de serveur ?

    Pour vérifier quelle version de serveur ton serveur utilise actuellement, utilise la commande suivante dans la console de ton serveur FiveM : `version`

    **Exemple**

    <Frame>
      ![version command example](/images/version_example.jpg)
    </Frame>

    ### Comment mettre à jour ma version de serveur ?

    Pour mettre à jour ta version de serveur, télécharge les nouveaux [server artifacts](https://runtime.fivem.net/artifacts/fivem/build_server_windows/master/) et extrais-les en remplaçant ceux de ton dossier serveur.

    Voici le guide **officiel** de [FiveM](https://docs.fivem.net/docs/server-manual/setting-up-a-server/) pour mettre à jour ton serveur.

    ### Ma version de serveur est déjà à jour, mais j'ai quand même l'erreur

    Si tu as l'erreur alors que ta version de serveur n'est pas le problème, consulte [Failed to verify protected resource](#failed-to-verify-protected-resource) ci-dessous.
  </Accordion>

  <Accordion title="Failed to verify protected resource">
    Exemple de message d'erreur :

    ```text
    [svadhesive] Failed to verify protected resource jobs_creator
    ```

    ### Raisons possibles

    En plus des [causes courantes](#causes-courantes) ci-dessus, cette erreur peut aussi se produire si :

    - Tu n'as pas de fichier `.fxap` dans le dossier du script

    ### Solutions

    <Steps>
      <Step title="Retélécharge le script">
        Télécharge à nouveau le script depuis [FiveM Portal](https://portal.cfx.re/).
      </Step>
      <Step title="Upload avec WinSCP">
        Upload le script en utilisant [WinSCP](https://winscp.net/eng/download.php) _au lieu de_ FileZilla.
      </Step>
      <Step title="Redémarre le serveur">
        Redémarre le serveur.
      </Step>
    </Steps>
  </Accordion>

  <Accordion title="You lack the required entitlement">
    Exemple de message d'erreur :

    ```text
    You lack the required entitlement to use script_name
    ```

    ### Raison

    Tous les scripts utilisant le système d'escrow de FiveM sont liés à ton compte FiveM (le compte que tu as utilisé sur Tebex).

    Pour fonctionner, le(s) script(s) nécessitent un serveur utilisant une server key créée par le même compte FiveM que celui utilisé sur Tebex.

    ### Qu'est-ce qu'une server key ?

    - La server key est générée sur [FiveM Portal](https://portal.cfx.re/)
    - La server key n'est **pas** une clé de script
    - Un serveur FiveM ne peut utiliser qu'**1** seule server key

    **Exemple d'une server key dans server.cfg**

    ```text
    sv_licenseKey "27ztq5g2pcjua67q4xywujkuzh5m7j4a"
    ```

    ### Comment vérifier ma server key ?

    Pour vérifier quelle server key ton serveur utilise actuellement, utilise la commande suivante dans la console de ton serveur FiveM : `sv_licenseKey`

    **Exemple :**

    <Frame>
      ![sv\_licenseKey example](/images/example_server_key.jpg)
    </Frame>

    ### Comment vérifier si j'utilise la bonne server key ?

    <Steps>
      <Step title="Récupère ta server key">
        Utilise la commande `sv_licenseKey` dans la console de ton serveur FiveM.
      </Step>
      <Step title="Note la server key">
        Note la **server key** que tu utilises actuellement.
      </Step>
      <Step title="Ouvre FiveM Keymaster">
        Va sur [FiveM Portal](https://portal.cfx.re/).
      </Step>
      <Step title="Vérifie la propriété du script">
        Vérifie si le compte avec lequel tu es connecté sur [FiveM Portal](https://portal.cfx.re/) possède le(s) script(s) que tu essaies d'utiliser. Si le script n'y figure pas, cela signifie que tu as utilisé un compte différent sur Tebex, ou que tu as transféré le script vers un autre compte.

        **Exemple avec le** [**script Jobs Creator**](https://forum.cfx.re/t/jobs-creator-4-6-esx-in-game-job-creation-menu-without-server-restart/2667762)

        <Frame>
          ![Jobs Creator ownership example](/images/example_purchased_assets.jpg)
        </Frame>
      </Step>
      <Step title="Vérifie le propriétaire de la server key">
        Si le compte que tu utilises sur [FiveM Portal](https://portal.cfx.re/) possède le(s) script(s), vérifie si la **server key** utilisée par ton serveur a été générée par ce même compte.

        <Frame>
          ![Server key owner example](/images/keymaster_keys_list.jpg)
        </Frame>
      </Step>
    </Steps>

    ### Ma server key a été générée par quelqu'un d'autre que moi, que puis-je faire ?

    Tu as 2 options :

    - Générer une clé depuis ton compte et l'utiliser
    - Transférer la propriété du script vers l'autre compte

    ### Comment transférer le script vers un autre compte ?

    Pour transférer le script vers un autre compte, rends-toi sur :

    [FiveM Portal](https://portal.cfx.re/) → onglet **Assets** → bouton rouge **Transfer to another account**

    <Warning>
      cfx.re a décidé que les scripts ne peuvent être transférés qu'1 seule fois, tu ne pourras donc pas transférer à nouveau le script.
    </Warning>

    ### Server key ZAP-Hosting

    Si tu utilises un serveur Zap-Hosting, tu n'as **pas** besoin d'entrer ta server key dans server.cfg, mais directement sur leur site web.

    [Voici le guide officiel de ZAP Hosting pour ça](https://zap-hosting.com/guides/docs/en/fivem_licensekey/).

    **Exemple de capture d'écran :**

    <Frame>
      ![ZAP Hosting license key example](/images/zap_hosting_custom_key.png)
    </Frame>
  </Accordion>

  <Accordion title="Que faire si rien ne résout les erreurs">
    ### J'ai suivi toutes les étapes mais rien ne fonctionne, que puis-je faire ?

    Si tu as suivi toutes les étapes, alors tu as simplement un virus sur ton serveur. Essaie de créer un serveur propre avec uniquement les scripts par défaut du framework et les scripts de jaksam.

    ### Comment vérifier si j'ai un virus sur mon serveur ?

    Ouvre le fichier mentionné par le script de jaksam avec le **bloc-notes**, et fais défiler jusqu'en bas. S'il y a du code partiellement lisible (par exemple `local...`), c'est un virus ajouté par autre chose, car normalement tout le fichier serait chiffré. Dans ce cas, tu devras résoudre ce problème avant de pouvoir utiliser un script.
  </Accordion>
</AccordionGroup>
