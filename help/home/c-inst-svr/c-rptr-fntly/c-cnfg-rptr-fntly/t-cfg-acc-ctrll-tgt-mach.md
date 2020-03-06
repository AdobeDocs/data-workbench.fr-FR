---
description: Les ordinateurs du serveur Target Insight Server exécutant le service de réplication Insight Server doivent être en mesure de lire les fichiers journaux sur ce serveur de répétition.
solution: Insight
title: Configuration du contrôle d’accès pour les machines Target
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration du contrôle d’accès pour les machines Target{#configuring-access-control-for-target-machines}

Les ordinateurs du serveur Target Insight Server exécutant le service de réplication Insight Server doivent être en mesure de lire les fichiers journaux sur ce serveur de répétition.

L&#39;accès aux ordinateurs cible est accordé à l&#39;aide du [!DNL Access Control.cfg] fichier.

**Pour configurer le contrôle d&#39;accès pour l&#39;accès par[!DNL Insight Server]les machines cibles**

1. Accédez au [!DNL Access Control] dossier du répertoire dans lequel vous avez installé la fonctionnalité de répéteur.

   Exemple : [!DNL D:\Adobe\Repeater\Access Control]

1. Ouvrez [!DNL Access Control.cfg] dans un éditeur de texte tel que le Bloc-notes.
1. Créez un groupe d’accès pour les [!DNL Insight Server] machines qui doivent accéder aux fichiers journaux sur ce serveur de répéteurs. Attribuez un nom à ce groupe d’accès, par exemple &quot;Cibles de réplication&quot;.

       Le fragment de fichier suivant montre à quoi doit ressembler le groupe d’accès.
       
       ```
       . . .
       6 = AccessGroup :
       Membres = vecteur : N éléments
     0 = chaîne : IP:Machine0IPA
 address     1 = chaîne : IP:Adresse
 Machine1IPA     . . .
       N = chaîne : IP:MachineNIPAddress
 Name     = chaîne : Cibles
 de réplication Accès en     lecture seule = vecteur: 1 élément
     0 = chaîne : EventDataLocation
 Accès     en lecture-écriture = vecteur : 0 élément
     . . .
       &quot;
   
   1. Dans la section Membres, spécifiez l’adresse IP de chaque ordinateur.
   1. Mettez à jour le nombre d’éléments pour le vecteur Membres afin de refléter le nombre d’adresses IP de l’ordinateur que vous avez insérées.
   1. Dans la section Accès en lecture seule, spécifiez l’emplacement des données d’événement auxquelles la réplication cible l’accès. Utilisez des barres obliques dans la spécification de chemin (/). L’emplacement par défaut est le [!DNL Logs] dossier sur l’ordinateur Répéteur (/Logs/).
   1. Mettez à jour le nombre d’éléments pour le vecteur Accès en lecture seule afin de refléter le nombre d’emplacements que vous avez insérés.

1. Mettez à jour le nombre de groupes d&#39;accès dans le vecteur Groupes de contrôle d&#39;accès en haut du fichier pour refléter l&#39;ajout du nouveau groupe d&#39;accès.

   ```
   Access Control Groups = vector: n items
   ```

1. Enregistrez le fichier.
