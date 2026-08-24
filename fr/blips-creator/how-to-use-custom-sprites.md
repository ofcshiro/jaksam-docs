---
title: "Comment utiliser des sprites personnalisés"
description: "Remplace les sprites de blip par défaut par tes propres icônes personnalisées."
icon: "image"
---

Blips Creator propose un moyen extrêmement simple de remplacer les sprites des blips.

<Steps>
  <Step title="Choisis une icône">
    Choisis une icône `.png` que tu veux utiliser (64x64px est idéal).
  </Step>
  <Step title="Ouvre le dossier des sprites">
    Va dans le dossier `blips_creator/_sprites/REPLACEABLE`.
  </Step>
  <Step title="Marque le sprite à remplacer">
    Choisis un sprite à remplacer, copie son nom, et ajoute un `#` avant le nom (pour le retrouver plus facilement plus tard si besoin).
  </Step>
  <Step title="Ajoute ton icône">
    Place la nouvelle icône avec le même nom que l'ancien sprite.
  </Step>
  <Step title="Redémarre le script">
    Redémarre Blips Creator **2 fois**.
  </Step>
</Steps>

## Exemple avec des images

Dans cet exemple, le logo vert est remplacé par le sprite rouge.

<Frame caption="Dossier blips_creator/_sprites/REPLACEABLE">
  ![REPLACEABLE folder](/images/immagine-1.png)
</Frame>

<Frame caption="Copie le nom du fichier">
  ![Copy the file name](/images/immagine-8.png)
</Frame>

<Frame caption='Ajoute un "#" avant le nom'>
  ![Add a hash before the name](/images/immagine-2.png)
</Frame>

<Frame caption="Renomme le fichier de ta nouvelle icône">
  ![Rename the new icon file](/images/immagine-4.png)
</Frame>

<Frame caption="Résultat final">
  ![Final result](/images/immagine-7.png)
</Frame>

Redémarre maintenant le script **2 fois** et le sprite est mis à jour.
