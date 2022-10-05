---
description: L’interface d’état détaillé de Data Workbench est utile pour résoudre les erreurs ou d’autres problèmes liés aux machines Data Workbench Server et Report Server qui sont des clients du serveur Data Workbench.
title: Affichage de l’état du serveur de rapports
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# Affichage de l’état du serveur de rapports{#displaying-report-server-status}

{{eol}}

L’interface d’état détaillé de Data Workbench est utile pour résoudre les erreurs ou d’autres problèmes liés aux machines Data Workbench Server et Report Server qui sont des clients du serveur Data Workbench.

Pour afficher l’état du rapport dans le [!DNL Master Server Detailed Status] , vous devez ajouter un serveur d’état de rapport à la variable [!DNL Servers] vectoriel dans le serveur Data Workbench [!DNL Communications.cfg] fichier . La procédure suivante décrit l’ajout du serveur d’état de rapport à la variable [!DNL Communications.cfg] fichier :

Pour plus d’informations sur [!DNL Detailed Status] , voir le chapitre Interfaces administratives de la section *Guide de l’utilisateur de Data Workbench*.

**Pour ajouter une[!DNL Report Status Server]**

1. Accédez au dossier Components dans le répertoire où vous avez installé le serveur Data Workbench (InsightServer64.exe).

   Exemple : [!DNL C:\Adobe\Server\Components]
1. Ouvrir [!DNL Communications.cfg] dans un éditeur de texte tel que le Bloc-notes.
1. Recherchez la variable [!DNL Servers] et ajoutez le serveur d’état du rapport à ce vecteur, comme indiqué dans le fragment de fichier suivant.

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

1. Mettez à jour le nombre d’éléments pour le [!DNL Servers] vectoriel (c’est-à-dire, incrémentez la valeur éléments d’une unité) comme indiqué dans le fragment de fichier de l’étape précédente.
1. Enregistrez le fichier.
