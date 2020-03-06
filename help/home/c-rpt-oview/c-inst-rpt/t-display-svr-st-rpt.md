---
description: L’interface d’état détaillé dans les outils de données est utile pour résoudre les erreurs ou d’autres problèmes liés aux serveurs Outils de données et aux serveurs de rapports qui sont des clients du serveur Outils de données.
solution: Analytics
title: Affichage de l’état du serveur de rapports
topic: Data workbench
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Affichage de l’état du serveur de rapports{#displaying-report-server-status}

L’interface d’état détaillé dans les outils de données est utile pour résoudre les erreurs ou d’autres problèmes liés aux serveurs Outils de données et aux serveurs de rapports qui sont des clients du serveur Outils de données.

Pour afficher l’état du rapport dans l’ [!DNL Master Server Detailed Status] interface, vous devez ajouter un serveur d’état de rapport au [!DNL Servers] vecteur dans le [!DNL Communications.cfg] fichier du serveur de l’outil de données. La procédure suivante décrit l’ajout du serveur d’état des rapports au [!DNL Communications.cfg] fichier :

Pour plus d’informations sur [!DNL Detailed Status] les interfaces, voir le chapitre Interfaces d’administration du Guide *de l’utilisateur des outils de* données.

**Pour ajouter une[!DNL Report Status Server]**

1. Accédez au dossier Composants du répertoire dans lequel vous avez installé le serveur de l’outil de données (InsightServer64.exe).

   Exemple : [!DNL C:\Adobe\Server\Components]
1. Ouvrez [!DNL Communications.cfg] dans un éditeur de texte tel que le Bloc-notes.
1. Localisez le [!DNL Servers] vecteur et ajoutez le serveur d’état du rapport à ce vecteur, comme indiqué dans le fragment de fichier suivant.

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

1. Mettez à jour le nombre d’éléments pour le [!DNL Servers] vecteur (c’est-à-dire, incrémentez la valeur des éléments d’une unité) comme l’indique le fragment de fichier à l’étape précédente.
1. Enregistrez le fichier.
