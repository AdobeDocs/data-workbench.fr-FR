---
description: Les machines de serveur Target Insight exécutant le service de réplication du serveur Insight doivent être en mesure de lire les fichiers journaux de ce serveur de répéteur.
title: Configuration du contrôle d’accès pour les machines cibles
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
exl-id: 2d0b554a-30e9-4344-9aec-a68fd5f57304
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 6%

---

# Configuration du contrôle d’accès pour les machines cibles{#configuring-access-control-for-target-machines}

Les machines de serveur Target Insight exécutant le service de réplication du serveur Insight doivent être en mesure de lire les fichiers journaux de ce serveur de répéteur.

L&#39;accès aux machines cibles est accordé à l&#39;aide du fichier [!DNL Access Control.cfg].

**Pour configurer le contrôle d’accès pour l’accès des  [!DNL Insight Server] machines cibles**

1. Accédez au dossier [!DNL Access Control] dans le répertoire où vous avez installé la fonctionnalité de répéteur.

   Exemple : [!DNL D:\Adobe\Repeater\Access Control]

1. Ouvrez [!DNL Access Control.cfg] dans un éditeur de texte tel que Notepad.
1. Créez un groupe d’accès pour les machines [!DNL Insight Server] qui doivent accéder aux fichiers journaux de ce serveur de répéteur. Donnez un nom à ce groupe d’accès, par exemple &quot;Cibles de réplication&quot;.

   Le fragment de fichier suivant montre à quoi le groupe d’accès doit ressembler.

   ```
   . . . 
     6 = AccessGroup: 
       Members = vector: N items 
         0 = string: IP:Machine0IPAddress 
         1 = string: IP:Machine1IPAddress 
   . . . 
         N = string: IP:MachineNIPAddress 
       Name = string: Replication Targets 
       Read-Only Access = vector: 1 items 
         0 = string: EventDataLocation 
       Read-Write Access = vector: 0 items 
   . . .
   ```

   1. Dans la section Membres , indiquez l’adresse IP de chaque ordinateur.
   1. Mettez à jour le nombre d’éléments pour le vecteur Membres afin de refléter le nombre d’adresses IP de la machine que vous avez insérées.
   1. Dans la section Accès en lecture seule , spécifiez l’emplacement des données d’événement auxquelles la réplication cible accès. Utilisez des barres obliques dans la spécification de chemin (/). L’emplacement par défaut est le dossier [!DNL Logs] sur l’ordinateur Répéteur (/Logs/).
   1. Mettez à jour le nombre d’éléments pour le vecteur Accès en lecture seule afin de refléter le nombre d’emplacements que vous avez insérés.

1. Mettez à jour le nombre de groupes d’accès dans le vecteur Groupes de contrôle d’accès situé en haut du fichier pour refléter l’ajout du nouveau groupe d’accès.

   ```
   Access Control Groups = vector: n items
   ```

1. Enregistrez le fichier.
