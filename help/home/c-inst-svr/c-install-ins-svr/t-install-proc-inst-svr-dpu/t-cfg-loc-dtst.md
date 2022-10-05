---
description: Par défaut, Insight Server écrit son jeu de données (temp.db) sur le même lecteur que les fichiers de programme du serveur Insight.
title: Configuration de l’emplacement du jeu de données (temp.db)
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
exl-id: 6812883f-ad51-4314-8c80-e95c3fe84664
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# Configuration de l’emplacement du jeu de données (temp.db){#configuring-the-location-of-the-dataset-temp-db}

{{eol}}

Par défaut, Insight Server écrit son jeu de données (temp.db) sur le même lecteur que les fichiers de programme du serveur Insight.

Par exemple, si vous installez [!DNL Insight Server] sur le lecteur C, il écrit le jeu de données pour le lecteur C.

Si vous voulez [!DNL Insight Server] pour gérer le jeu de données sur un autre lecteur ou si la quantité de données que vous prévoyez de collecter nécessite l’utilisation de plusieurs lecteurs, vous devez mettre à jour la variable [!DNL Disk Files.cfg] pour spécifier l’emplacement souhaité [!DNL Insight Server] pour écrire la variable [!DNL temp.db] fichier .

**Pour configurer l’emplacement de temp.db**

1. Accédez au [!DNL Components] dans le répertoire où vous avez installé [!DNL Insight Server].

   Exemple : [!DNL C:\Adobe\Server\Components]

1. Ouvrez le [!DNL Disk Files.cfg] dans un éditeur de texte tel que le Bloc-notes.

   Par défaut, ce fichier contient une seule entrée dans la structure Fichiers disque , comme illustré ci-dessous.

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. Pour modifier l’emplacement de [!DNL temp.db], modifiez la définition des fichiers de disque. L’exemple suivant illustre la modification de la configuration pour diffuser la variable [!DNL temp.db] sur les lecteurs C, D et E :

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
   >Notez l’utilisation de deux barres obliques inverses dans les noms de fichier ci-dessus. Dans [!DNL Insight Server] fichiers de configuration, la barre oblique inverse est un caractère d’échappement. Il est utilisé pour exprimer des séquences de contrôle spéciales (par exemple, \t pour un caractère de tabulation) dans du texte. Pour représenter un caractère de barre oblique inverse, vous devez saisir la barre oblique inverse deux fois (par exemple, \\) pour remplacer la fonction d’échappement. Cela s’applique uniquement lors de la modification de fichiers de configuration dans un éditeur de texte tel que le Bloc-notes.
