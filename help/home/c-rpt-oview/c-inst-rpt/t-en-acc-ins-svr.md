---
description: Pour se connecter à un serveur Data Workbench, le serveur de rapports doit disposer des autorisations d’accès à ce serveur.
title: Activation de l’accès au serveur Data Workbench
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
exl-id: bf409413-470e-4e05-9bd2-b5b511bbe4a5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 6%

---

# Activation de l’accès au serveur Data Workbench{#enabling-access-to-the-data-workbench-server}

Pour se connecter à un serveur Data Workbench, le serveur de rapports doit disposer des autorisations d’accès à ce serveur.

Vous accordez l’accès à un serveur Data Workbench en ajoutant le nom commun du serveur de rapports (tel qu’il est attribué sur le certificat numérique du serveur de rapports) au fichier de contrôle d’accès du serveur.

>[!NOTE]
>
>Lorsque vous travaillez dans un environnement organisé en grappes, le serveur de rapports doit être configuré pour accéder au serveur Data Workbench principal afin d’éviter des problèmes de synchronisation. Dans Data Workbench, vous pouvez afficher des informations sur les serveurs de traitement de votre grappe à l’aide de l’option de menu [!DNL Related Servers] dans la balise [!DNL Servers Manager]. Pour plus d’informations sur [!DNL Servers Manager], consultez le chapitre Interfaces d’administration du *Guide de l’utilisateur du Data Workbench*.

La procédure suivante décrit l’ajout manuel d’un serveur de rapports au fichier de contrôle d’accès sur un serveur Data Workbench. Pour mettre à jour le fichier de contrôle d’accès de cette manière, vous devez disposer d’un accès au système de fichiers sur l’ordinateur sur lequel le serveur Data Workbench est installé.

Vous pouvez également mettre à jour le fichier de contrôle d’accès du serveur à l’aide de [!DNL Server Files Manager] dans Data Workbench. Pour ce faire, votre client Data Workbench doit disposer de droits d’administrateur sur le serveur.

Pour plus d’informations sur [!DNL Server Files Manager], consultez le chapitre Interfaces d’administration du *Guide de l’utilisateur du Data Workbench*.

**Pour configurer l’accès à un serveur Data Workbench**

1. Accédez au dossier Access Control dans le répertoire où vous avez installé le serveur Data Workbench (InsightServer64.exe).

   Exemple : [!DNL C:\Adobe\Server\Access Control]

1. Ouvrez [!DNL Access Control.cfg] dans un éditeur de texte tel que Notepad.
1. Recherchez [!DNL Report Server AccessGroup] et ajoutez le nom commun [!DNL Report Server’s] à ce groupe, comme indiqué dans le fragment de fichier suivant. (Saisissez le nom commun tel qu’il apparaît sur le certificat numérique [!DNL Report Server’s].)

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
