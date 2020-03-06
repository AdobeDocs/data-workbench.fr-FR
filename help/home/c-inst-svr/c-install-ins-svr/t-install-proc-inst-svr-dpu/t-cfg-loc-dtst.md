---
description: Par défaut, Insight Server écrit son jeu de données (temp.db) sur le même lecteur que les fichiers programme du serveur Insight.
solution: Insight
title: Configuration de l'emplacement du jeu de données (temp.db)
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration de l&#39;emplacement du jeu de données (temp.db){#configuring-the-location-of-the-dataset-temp-db}

Par défaut, Insight Server écrit son jeu de données (temp.db) sur le même lecteur que les fichiers programme du serveur Insight.

Par exemple, si vous installez [!DNL Insight Server] sur le lecteur C, il écrit le jeu de données sur le lecteur C.

Si vous souhaitez [!DNL Insight Server] conserver le jeu de données sur un autre lecteur ou si la quantité de données que vous prévoyez de collecter nécessite l&#39;utilisation de plusieurs lecteurs, vous devez mettre à jour le [!DNL Disk Files.cfg] fichier afin de spécifier l&#39;endroit où vous souhaitez [!DNL Insight Server] écrire le [!DNL temp.db] fichier.

**Pour configurer l’emplacement de temp.db**

1. Accédez au [!DNL Components] dossier du répertoire dans lequel vous avez installé [!DNL Insight Server].

   Exemple : [!DNL C:\Adobe\Server\Components]

1. Ouvrez le [!DNL Disk Files.cfg] fichier dans un éditeur de texte tel que le Bloc-notes.

   Par défaut, ce fichier contient une seule entrée dans la structure Fichiers disque, comme illustré ci-dessous.

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. Pour modifier l&#39;emplacement de [!DNL temp.db], modifiez la définition des fichiers disque. L&#39;exemple suivant illustre la modification de la configuration pour répartir le [!DNL temp.db] fichier sur les lecteurs C, D et E :

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
   >Notez l’utilisation des barres obliques inverses doubles dans les noms de fichier ci-dessus. Dans [!DNL Insight Server] les fichiers de configuration, la barre oblique inverse est un caractère d’échappement. Il est utilisé pour exprimer des séquences de commandes spéciales (par exemple, \t pour un caractère de tabulation) dans du texte. Pour représenter une barre oblique inverse, vous devez taper la barre oblique inverse deux fois (par exemple, \\) pour remplacer la fonction d&#39;échappement. Cela s’applique uniquement lors de la modification des fichiers de configuration dans un éditeur de texte tel que le Bloc-notes.

