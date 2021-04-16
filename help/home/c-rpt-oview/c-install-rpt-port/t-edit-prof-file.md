---
description: Pour spécifier les profils qui doivent être disponibles dans le portail de rapports, vous devez configurer le fichier profils.xml.
title: Modifier le fichier Profiles.xml
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
exl-id: 7a3900e4-e472-4295-80f7-ce755958bc18
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 7%

---

# Modifier le fichier Profiles.xml{#edit-the-profiles-xml-file}

Pour spécifier les profils qui doivent être disponibles dans le portail de rapports, vous devez configurer le fichier profils.xml.

Le fichier [!DNL profiles.xml] réside dans le dossier que vous avez désigné pour la sortie. Par défaut, il réside dans le dossier \*PortalName*\PortalFiles\Output folder.

**Pour ajouter des noms de profil au fichier profils.xml**

1. Sur l’ordinateur sur lequel IIS est en cours d’exécution, ouvrez le fichier [!DNL profiles.xml] dans un éditeur de texte tel que le Bloc-notes.
1. Ajoutez un élément de profil et une balise pour chaque [!DNL Profile] dans votre portail, comme dans l&#39;exemple suivant :

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

1. Enregistrez et fermez le fichier.
