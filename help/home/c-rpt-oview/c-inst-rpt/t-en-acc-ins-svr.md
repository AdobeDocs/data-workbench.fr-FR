---
description: Pour se connecter à un serveur Data Workbench, le serveur de rapports doit disposer des autorisations d’accès à ce serveur.
title: Activation de l’accès au serveur Data Workbench
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
exl-id: bf409413-470e-4e05-9bd2-b5b511bbe4a5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 6%

---

# Activation de l’accès au serveur Data Workbench{#enabling-access-to-the-data-workbench-server}

{{eol}}

Pour se connecter à un serveur Data Workbench, le serveur de rapports doit disposer des autorisations d’accès à ce serveur.

Vous accordez l’accès à un serveur Data Workbench en ajoutant le nom commun du serveur de rapports (tel qu’il est attribué sur le certificat numérique du serveur de rapports) au fichier de contrôle d’accès du serveur.

>[!NOTE]
>
>Lorsque vous travaillez dans un environnement organisé en grappes, le serveur de rapports doit être configuré pour accéder au serveur Data Workbench principal afin d’éviter des problèmes de synchronisation. Dans Data Workbench, vous pouvez afficher des informations sur les serveurs de traitement de votre grappe à l’aide de la fonction [!DNL Related Servers] dans le menu [!DNL Servers Manager]. Pour plus d’informations sur la variable [!DNL Servers Manager], voir le chapitre Interfaces administratives de la section *Guide de l’utilisateur de Data Workbench*.

La procédure suivante décrit l’ajout manuel d’un serveur de rapports au fichier de contrôle d’accès sur un serveur Data Workbench. Pour mettre à jour le fichier de contrôle d’accès de cette manière, vous devez disposer d’un accès au système de fichiers sur l’ordinateur sur lequel le serveur Data Workbench est installé.

Vous pouvez également mettre à jour le fichier de contrôle d’accès du serveur à l’aide de la variable [!DNL Server Files Manager] dans data workbench. Pour ce faire, votre client Data Workbench doit disposer de droits d’administrateur sur le serveur.

Pour plus d’informations sur la variable [!DNL Server Files Manager], voir le chapitre Interfaces administratives de la section *Guide de l’utilisateur de Data Workbench*.

**Pour configurer l’accès à un serveur Data Workbench**

1. Accédez au dossier Access Control dans le répertoire où vous avez installé le serveur Data Workbench (InsightServer64.exe).

   Exemple : [!DNL C:\Adobe\Server\Access Control]

1. Ouvrir [!DNL Access Control.cfg] dans un éditeur de texte tel que le Bloc-notes.
1. Recherchez la variable [!DNL Report Server AccessGroup] et ajouter [!DNL Report Server’s] nom commun à ce groupe, comme indiqué dans le fragment de fichier suivant. (Saisissez le nom commun tel qu’il apparaît sur [!DNL Report Server’s] certificat numérique.)

   ```
   . . .
     5 = AccessGroup: 
       Members = vector: 1 items
         0 = string: CN: ReportCommonName
       Name = string: Report Server
       Read-Only Access = vector: 5 items
         0 = string: /Profiles/$
         1 = string: /Status/
         3 = string: /Software/
         4 = string: /Addresses/
         5 = string: /Users/$
       Read-Write Access = vector: 3 items
         0 = string: /Profiles/
         1 = string: /Users/%CN%/
         2 = string: /ReportStatus.vsp
      . . .
   ```

1. Enregistrez le fichier.
