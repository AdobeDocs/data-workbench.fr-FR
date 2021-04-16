---
description: Par défaut, Insight Server écrit son jeu de données (temp.db) sur le même lecteur que les fichiers de programme du serveur Insight.
title: Configuration de l’emplacement du jeu de données (temp.db)
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
exl-id: 6812883f-ad51-4314-8c80-e95c3fe84664
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# Configuration de l’emplacement du jeu de données (temp.db){#configuring-the-location-of-the-dataset-temp-db}

Par défaut, Insight Server écrit son jeu de données (temp.db) sur le même lecteur que les fichiers de programme du serveur Insight.

Par exemple, si vous installez [!DNL Insight Server] sur le lecteur C, il écrit le jeu de données sur le lecteur C.

Si vous souhaitez que [!DNL Insight Server] conserve le jeu de données sur un autre lecteur ou si la quantité de données que vous prévoyez de collecter nécessite l&#39;utilisation de plusieurs lecteurs, vous devez mettre à jour le fichier [!DNL Disk Files.cfg] pour spécifier où [!DNL Insight Server] doit écrire le fichier [!DNL temp.db].

**Pour configurer l’emplacement de temp.db**

1. Accédez au dossier [!DNL Components] dans le répertoire où vous avez installé [!DNL Insight Server].

   Exemple : [!DNL C:\Adobe\Server\Components]

1. Ouvrez le fichier [!DNL Disk Files.cfg] dans un éditeur de texte tel que le Bloc-notes.

   Par défaut, ce fichier contient une entrée unique dans la structure Fichiers disque, comme illustré ci-dessous.

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. Pour modifier l&#39;emplacement de [!DNL temp.db], modifiez la définition des fichiers de disque. L&#39;exemple suivant illustre comment modifier la configuration pour répartir le fichier [!DNL temp.db] sur les lecteurs C, D et E :

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 3 items
       0 = string: C:\\Temp\\temp.db
       1 = string: D:\\Temp\\temp.db
       2 = string: E:\\Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

   >[!NOTE]
   >
   >Notez l’utilisation des barres obliques inverses de doublon dans les noms de fichier ci-dessus. Dans les fichiers de configuration [!DNL Insight Server], la barre oblique inverse est un caractère d’échappement. Il est utilisé pour exprimer des séquences de commandes spéciales (par exemple, \t pour un caractère de tabulation) dans du texte. Pour représenter une barre oblique inverse réelle, vous devez taper la barre oblique inverse deux fois (par exemple, \\) pour remplacer la fonction d&#39;échappement. Cela s’applique uniquement lors de la modification des fichiers de configuration dans un éditeur de texte tel que le Bloc-notes.
