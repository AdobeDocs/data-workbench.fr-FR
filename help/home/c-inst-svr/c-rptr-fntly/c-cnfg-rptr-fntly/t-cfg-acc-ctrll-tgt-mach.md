---
description: Les ordinateurs Cible Insight Server exécutant le service de réplication Insight Server doivent être en mesure de lire les fichiers journaux sur ce serveur de répéteurs.
solution: Insight
title: Configuration du contrôle d’accès pour les machines cibles
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
translation-type: tm+mt
source-git-commit: 0276701151d1403926ce184069526ebdf3e28e36
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 6%

---


# Configuration du contrôle d’accès pour les machines cibles{#configuring-access-control-for-target-machines}

Les ordinateurs Cible Insight Server exécutant le service de réplication Insight Server doivent être en mesure de lire les fichiers journaux sur ce serveur de répéteurs.

L&#39;accès aux machines de cible est accordé à l&#39;aide du [!DNL Access Control.cfg] fichier.

**Pour configurer le Contrôle d&#39;accès pour l&#39;accès des machines cible[!DNL Insight Server]**

1. Accédez au [!DNL Access Control] dossier du répertoire dans lequel vous avez installé la fonctionnalité de répéteur.

   Exemple : [!DNL D:\Adobe\Repeater\Access Control]

1. Ouvrez [!DNL Access Control.cfg] dans un éditeur de texte tel que le Bloc-notes.
1. Créez un groupe d’accès pour les machines [!DNL Insight Server] qui doivent accéder aux fichiers journaux sur ce serveur de répéteurs. Attribuez un nom à ce groupe d’accès, par exemple &quot;Cibles de réplication&quot;.

   Le fragment de fichier suivant montre à quoi doit ressembler le groupe d&#39;accès.

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

   1. Dans la section Membres, spécifiez l&#39;adresse IP de chaque ordinateur.
   1. Mettez à jour le nombre d&#39;éléments pour le vecteur Membres afin de refléter le nombre d&#39;adresses IP de l&#39;ordinateur que vous avez insérées.
   1. Dans la section Accès en lecture seule, spécifiez l&#39;emplacement des données de événement auxquelles les cibles de réplication accèdent. Utilisez des barres obliques dans la spécification de chemin (/). L’emplacement par défaut est le [!DNL Logs] dossier sur l’ordinateur Répéteur (/Logs/).
   1. Mettez à jour le nombre d&#39;éléments pour le vecteur Accès en lecture seule afin de refléter le nombre d&#39;emplacements que vous avez insérés.

1. Mettez à jour le nombre de groupes d&#39;accès dans le vecteur Groupes de Contrôles d&#39;accès situé en haut du fichier afin de refléter l&#39;ajout du nouveau groupe d&#39;accès.

   ```
   Access Control Groups = vector: n items
   ```

1. Enregistrez le fichier.
