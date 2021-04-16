---
description: L’interface d’état détaillé dans l’outil de données est utile pour résoudre les erreurs ou d’autres problèmes avec les ordinateurs du serveur de Data Workbench et du serveur de rapports qui sont des clients du serveur de Data Workbench.
title: Affichage de l’état du serveur de rapports
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# Affichage de l’état du serveur de rapports{#displaying-report-server-status}

L’interface d’état détaillé dans l’outil de données est utile pour résoudre les erreurs ou d’autres problèmes avec les ordinateurs du serveur de Data Workbench et du serveur de rapports qui sont des clients du serveur de Data Workbench.

Pour vue l’état du rapport dans l’interface [!DNL Master Server Detailed Status], vous devez ajouter un serveur d’état de rapport au vecteur [!DNL Servers] dans le fichier [!DNL Communications.cfg] du serveur de l’outil de données. La procédure suivante décrit l&#39;ajout du serveur d&#39;état de rapport au fichier [!DNL Communications.cfg] :

Pour plus d&#39;informations sur les interfaces [!DNL Detailed Status], consultez le chapitre Interfaces d&#39;administration du *Guide de l&#39;utilisateur Data Workbench*.

**Pour ajouter une[!DNL Report Status Server]**

1. Accédez au dossier Composants du répertoire dans lequel vous avez installé le serveur de l’outil de données (InsightServer64.exe).

   Exemple : [!DNL C:\Adobe\Server\Components]
1. Ouvrez [!DNL Communications.cfg] dans un éditeur de texte tel que le Bloc-notes.
1. Recherchez le vecteur [!DNL Servers] et ajoutez le serveur d’état de rapport à ce vecteur, comme indiqué dans le fragment de fichier suivant.

   ```
    . . .
   Servers = vector: 17 items
       0 = FileServer: 
         Local Path = string: Audit\\
         URI = string: /Audit
       1 = FileServer: 
         Local Path = string: Bin\\
         URI = string: /Bin
       2 = FileServer: 
         Local Path = string: Components\\
         URI = string: /Components
     . . .
       16 = ReportStatusServer: 
         URI = string: /ReportStatus.vsp
   ```

1. Mettez à jour le nombre d’éléments pour le vecteur [!DNL Servers] (c’est-à-dire, incrémentez la valeur des éléments d’une unité) comme indiqué dans le fragment de fichier à l’étape précédente.
1. Enregistrez le fichier.
