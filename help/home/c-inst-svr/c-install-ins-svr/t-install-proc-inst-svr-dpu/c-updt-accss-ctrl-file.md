---
description: Le fichier Contrôle d'accès.cfg gère l’accès à certaines fonctionnalités d’Insight Server.
title: Mise à jour du fichier de contrôle d’accès
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---

# Mise à jour du fichier de contrôle d’accès{#updating-the-access-control-file}

Le fichier Contrôle d&#39;accès.cfg gère l’accès à certaines fonctionnalités d’Insight Server.

Il définit des entités appelées AccessGroups. Un groupe AccessGroup identifie un groupe d&#39;utilisateurs autorisés à utiliser certaines fonctionnalités du serveur.

Avant de pouvoir vous connecter à [!DNL Insight Server] avec [!DNL Insight], vous devez mettre à jour le groupe d&#39;accès Administrateurs afin d&#39;inclure l&#39;une des licences [!DNL Insight] que l&#39;Adobe a délivrées à votre organisation. Ce AccessGroup identifie les utilisateurs autorisés à exécuter des fonctions administratives par [!DNL Insight].

La procédure suivante décrit comment ajouter une licence au groupe d&#39;accès Administrateurs. Pour terminer cette tâche, vous devez déterminer quelle licence [!DNL Insight] possède des privilèges d’administration pour votre entreprise. (Pour la configuration et la configuration initiales, accorder des privilèges d’administration à une seule licence suffit. Vous pourrez ultérieurement accorder des privilèges d’administration à d’autres licences.) Vous devez également connaître le &quot;nom commun&quot; attribué à cette licence. Pour obtenir cette valeur, vous pouvez examiner les certificats de licence de votre compte à l’adresse [https://aap.adobe.com](https://aap.adobe.com).

L&#39;objectif de cette procédure est simplement d&#39;identifier une copie sous licence de [!DNL Insight] que vous pouvez utiliser pour configurer et configurer initialement [!DNL Insight Server]. Une fois que vous avez identifié cette licence, vous pouvez effectuer toutes les configurations de serveur suivantes (y compris la configuration AccessGroup supplémentaire) en utilisant la copie sous licence de [!DNL Insight]. Pour plus d&#39;informations sur le contrôle de l&#39;accès au serveur à l&#39;aide d&#39;AccessGroups, voir [Configuration du Contrôle d&#39;accès](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**Pour mettre à jour le fichier de contrôle d&#39;accès**

1. Accédez au dossier [!DNL Access Control] dans le répertoire où vous avez installé [!DNL Insight Server].

   Exemple : [!DNL C:\Adobe\Server\Access Control]

1. Ouvrez le fichier [!DNL Access Control.cfg] dans un éditeur de texte tel que le Bloc-notes.
1. Localisez l&#39;entrée CN dans le groupe d&#39;accès Administrateurs et remplacez la valeur existante de cette entrée par le nom commun qui identifie l&#39;[!DNL Insight] que vous utiliserez pour configurer et administrer initialement [!DNL Insight Server]. Le fragment de fichier suivant illustre l&#39;emplacement où vous insérez le nom commun dans le fichier [!DNL Access Control.cfg].

   ```
   Access Control Groups = vector: 5 items 
     0 = AccessGroup: 
       Members = vector: 2 items 
         0 = string: IP:127.0.0.1 
         1 = string: CN: CommonName 
       Name = string: Administrators 
       Read-Only Access = vector: 0 items 
       Read-Write Access = vector: 1 items 
         0 = string: / 
     1 = AccessGroup: 
     . . . 
   ```

   Si vous utilisez l’authentification basée sur les informations d’identification, quelques entrées supplémentaires seront disponibles pour la configuration. Ces entrées sont les suivantes :

   * O (ID d’organisation) : Cette entrée représente l&#39;ID de l&#39;organisation. Par exemple : `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. Cet identifiant se trouve dans le Admin Console.
   * PLC - Cette entrée permet d&#39;accéder aux utilisateurs configurés pour une configuration de produit particulière. Il peut être utilisé au format `Organization_Id-PLC`. Par exemple : `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. Les utilisateurs configurés pour le Data Workbench à l&#39;aide du PLC `DataworkbenchAdminUsers` auront accès à leurs serveurs.
   * Courriel : cette entrée permet d&#39;accéder à tout utilisateur individuel. Sa valeur doit être l’adresse électronique de l’utilisateur ayant reçu les privilèges d’accès. Par exemple : `1 = string: Email:kim@exampleorg.com`.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Les entrées sont sensibles à la casse. Vous devez vous assurer que les valeurs spécifiées pour O, PLC et Email sont exactement les mêmes que celles indiquées dans le Admin Console.
   >    * Tapez le nom commun tel qu&#39;il apparaît sur le certificat.
   >    * N&#39;utilisez pas la touche de tabulation pour générer des espaces dans le fichier [!DNL Access Control.cfg] (ou dans tout autre fichier de configuration pour un composant d&#39;Adobe). Utilisez uniquement des espaces pour créer des espaces blancs. Un caractère de tabulation empêche le système de lire correctement le fichier.


1. Enregistrez et fermez le fichier.
