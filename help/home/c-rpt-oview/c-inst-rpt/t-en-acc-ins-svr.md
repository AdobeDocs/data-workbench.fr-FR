---
description: Pour se connecter à un serveur d’outils de données, Report Server doit disposer des autorisations nécessaires pour accéder à ce serveur.
title: Activation de l’accès au serveur Data Workbench
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
exl-id: bf409413-470e-4e05-9bd2-b5b511bbe4a5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 6%

---

# Activation de l’accès au serveur Data Workbench{#enabling-access-to-the-data-workbench-server}

Pour se connecter à un serveur d’outils de données, Report Server doit disposer des autorisations nécessaires pour accéder à ce serveur.

Vous accordez l’accès à un serveur de l’outil de données en ajoutant le nom commun du serveur de rapports (tel qu’il est attribué sur le certificat numérique du serveur de rapports) au fichier de contrôle d&#39;accès du serveur.

>[!NOTE]
>
>Lorsque vous travaillez dans un environnement organisé en grappes, le serveur de rapports doit être configuré pour accéder au serveur de l’outil de données maître afin d’éviter les problèmes de synchronisation. Dans l’outil de données, vous pouvez vue des informations sur les serveurs de traitement de votre grappe à l’aide de l’option de menu [!DNL Related Servers] dans le [!DNL Servers Manager]. Pour plus d&#39;informations sur [!DNL Servers Manager], consultez le chapitre Interfaces d&#39;administration du *Guide de l&#39;utilisateur Data Workbench*.

La procédure suivante décrit comment ajouter manuellement le serveur de rapports au fichier de contrôle d&#39;accès sur un serveur de outils de données. Pour mettre à jour le fichier de contrôle d&#39;accès de cette façon, vous devez disposer d’un accès au système de fichiers sur l’ordinateur sur lequel le serveur de l’outil de données est installé.

Vous pouvez également mettre à jour le fichier de contrôle d&#39;accès du serveur à l’aide de [!DNL Server Files Manager] dans l’outil de données. Pour ce faire, votre client Outils de données doit disposer de privilèges d’administration sur le serveur.

Pour plus d&#39;informations sur [!DNL Server Files Manager], consultez le chapitre Interfaces d&#39;administration du *Guide de l&#39;utilisateur Data Workbench*.

**Pour configurer l’accès à un serveur de l’outil de données**

1. Accédez au dossier Contrôle d&#39;accès du répertoire dans lequel vous avez installé le serveur de l’outil de données (InsightServer64.exe).

   Exemple : [!DNL C:\Adobe\Server\Access Control]

1. Ouvrez [!DNL Access Control.cfg] dans un éditeur de texte tel que le Bloc-notes.
1. Recherchez [!DNL Report Server AccessGroup] et ajoutez le nom commun [!DNL Report Server’s] à ce groupe, comme indiqué dans le fragment de fichier suivant. (Tapez le nom commun tel qu&#39;il apparaît sur le certificat numérique [!DNL Report Server’s].)

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
