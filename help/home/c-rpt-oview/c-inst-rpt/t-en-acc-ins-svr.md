---
description: Pour se connecter à un serveur de l’outil de données, le serveur de rapports doit avoir l’autorisation d’accéder à ce serveur.
solution: Analytics
title: Activation de l’accès au serveur des outils de données
topic: Data workbench
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Activation de l’accès au serveur des outils de données{#enabling-access-to-the-data-workbench-server}

Pour se connecter à un serveur de l’outil de données, le serveur de rapports doit avoir l’autorisation d’accéder à ce serveur.

Vous accordez l’accès à un serveur de outils de données en ajoutant le nom commun du serveur de rapports (tel qu’il est affecté sur le certificat numérique du serveur de rapports) au fichier de contrôle d’accès du serveur.

>[!NOTE]
>
>Lorsque vous travaillez dans un environnement organisé en grappes, le serveur de rapports doit être configuré pour accéder au serveur maître des outils de données afin d’éviter des problèmes de synchronisation. Dans les outils de données, vous pouvez afficher des informations sur les serveurs de traitement de votre grappe à l’aide de l’ [!DNL Related Servers] option de menu dans le [!DNL Servers Manager]. Pour plus d’informations sur la [!DNL Servers Manager]solution, voir le chapitre Interfaces d’administration du Guide *de l’utilisateur des outils de* données.

La procédure suivante décrit l’ajout manuel du serveur de rapports au fichier de contrôle d’accès sur un serveur de outils de données. Pour mettre à jour le fichier de contrôle d’accès de cette manière, vous devez disposer d’un accès au système de fichiers sur l’ordinateur sur lequel le serveur de l’outil de données est installé.

Vous pouvez également mettre à jour le fichier de contrôle d’accès du serveur à l’aide de l’outil [!DNL Server Files Manager] de données. Pour ce faire, votre client Outils de données doit disposer de privilèges d’administration sur le serveur.

Pour plus d’informations sur la [!DNL Server Files Manager]solution, voir le chapitre Interfaces d’administration du Guide *de l’utilisateur des outils de* données.

**Pour configurer l’accès à un serveur de l’outil de données**

1. Accédez au dossier Access Control dans le répertoire où vous avez installé le serveur de l’outil de données (InsightServer64.exe).

   Exemple : [!DNL C:\Adobe\Server\Access Control]

1. Ouvrez [!DNL Access Control.cfg] dans un éditeur de texte tel que le Bloc-notes.
1. Localisez le groupe [!DNL Report Server AccessGroup] et ajoutez-lui [!DNL Report Server’s] un nom commun, comme indiqué dans le fragment de fichier suivant. (Entrez le nom commun tel qu’il apparaît sur le certificat [!DNL Report Server’s] numérique.)

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
