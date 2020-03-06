---
description: Pour spécifier les profils que vous souhaitez voir disponibles dans le portail de rapports, vous devez configurer le fichier profiles.xml.
solution: Analytics
title: Modification du fichier Profiles.xml
topic: Data workbench
uuid: 3640552b-bc46-4b4f-8524-e021b0ca2bfc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modification du fichier Profiles.xml{#edit-the-profiles-xml-file}

Pour spécifier les profils que vous souhaitez voir disponibles dans le portail de rapports, vous devez configurer le fichier profiles.xml.

Le [!DNL profiles.xml] fichier réside dans le dossier que vous avez désigné pour la sortie. Par défaut, il réside dans le dossier \*PortalName*\PortalFiles\Output folder.

**Pour ajouter des noms de profil au fichier profiles.xml**

1. Sur l’ordinateur sur lequel IIS est en cours d’exécution, ouvrez le [!DNL profiles.xml] fichier dans un éditeur de texte tel que le Bloc-notes.
1. Ajoutez un élément de profil et une balise pour chaque élément [!DNL Profile] de votre portail, comme dans l’exemple suivant :

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
