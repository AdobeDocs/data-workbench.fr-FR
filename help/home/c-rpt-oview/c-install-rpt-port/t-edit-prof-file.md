---
description: Pour spécifier les profils qui doivent être disponibles dans le portail de rapports, vous devez configurer le fichier profiles.xml .
title: Modifier le fichier Profiles.xml
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 7%

---

# Modifier le fichier Profiles.xml{#edit-the-profiles-xml-file}

{{eol}}

Pour spécifier les profils qui doivent être disponibles dans le portail de rapports, vous devez configurer le fichier profiles.xml .

Le [!DNL profiles.xml] réside dans le dossier que vous avez désigné pour la sortie. Par défaut, il réside dans le dossier \*PortalName*\PortalFiles\Output.

**Pour ajouter des noms de profil au fichier profiles.xml**

1. Sur l’ordinateur sur lequel IIS est en cours d’exécution, ouvrez le [!DNL profiles.xml] dans un éditeur de texte tel que le Bloc-notes.
1. Ajout d’un élément de profil et d’une balise pour chacun d’eux [!DNL Profile] dans votre portail, comme dans l’exemple suivant :

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <PROFILES>
     <PROFILE>
       <NAME>Product Sales</NAME>
     </PROFILE>
     <PROFILE>
       <NAME>Product Marketing</NAME>
     </PROFILE>
   </PROFILES>
   ```

1. Enregistrez le fichier, puis fermez-le.
