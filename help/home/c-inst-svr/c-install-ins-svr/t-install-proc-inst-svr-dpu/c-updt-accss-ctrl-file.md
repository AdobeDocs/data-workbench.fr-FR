---
description: Le fichier Access Control.cfg gère l’accès à certaines fonctionnalités du serveur Insight.
title: Mise à jour du fichier de contrôle d’accès
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
exl-id: 551758c1-f24b-49e6-ab6e-09979511e4f4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---

# Mise à jour du fichier de contrôle d’accès{#updating-the-access-control-file}

{{eol}}

Le fichier Access Control.cfg gère l’accès à certaines fonctionnalités du serveur Insight.

Il définit des entités appelées AccessGroups. Un groupe d’accès identifie un groupe d’utilisateurs autorisés à utiliser certaines fonctionnalités du serveur.

Avant de vous connecter à [!DNL Insight Server] avec [!DNL Insight], vous devez mettre à jour le groupe d’accès Administrateurs afin d’inclure l’un des [!DNL Insight] licences délivrées par l’Adobe à votre organisation. Ce groupe d’accès identifie les utilisateurs autorisés à exécuter des fonctions administratives via [!DNL Insight].

La procédure suivante décrit comment ajouter une licence au groupe d’accès Administrateurs. Pour terminer cette tâche, vous devez déterminer laquelle [!DNL Insight] la licence dispose de privilèges d’administrateur pour votre organisation. (Pour la configuration et la configuration initiales, accorder des privilèges d’administrateur à une seule licence suffit. Vous pourrez ultérieurement accorder des privilèges d’administrateur à des licences supplémentaires.) Vous devez également connaître le &quot;nom commun&quot; attribué à cette licence. Pour obtenir cette valeur, vous pouvez consulter les certificats de licence de votre compte à l’adresse [https://aap.adobe.com](https://aap.adobe.com).

L’objectif de cette procédure est simplement d’identifier une copie sous licence de [!DNL Insight] que vous pouvez utiliser pour configurer et configurer initialement [!DNL Insight Server]. Une fois cette licence identifiée, vous pouvez effectuer toutes les configurations de serveur suivantes (y compris la configuration AccessGroup supplémentaire) à l’aide de la copie sous licence de [!DNL Insight]. Pour plus d’informations sur le contrôle de l’accès au serveur à l’aide d’AccessGroups, voir [Configuration du contrôle d’accès](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**Pour mettre à jour le fichier de contrôle d’accès**

1. Accédez au [!DNL Access Control] dans le répertoire où vous avez installé [!DNL Insight Server].

   Exemple : [!DNL C:\Adobe\Server\Access Control]

1. Ouvrez le [!DNL Access Control.cfg] dans un éditeur de texte tel que le Bloc-notes.
1. Localisez l’entrée CN dans le groupe d’accès Administrateurs et remplacez la valeur existante de cette entrée par le nom commun qui identifie la variable [!DNL Insight] que vous utiliserez pour configurer et administrer initialement [!DNL Insight Server]. Le fragment de fichier suivant illustre l’emplacement où vous insérez le nom commun dans le [!DNL Access Control.cfg] fichier .

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

   * O (ID d’organisation) : Cette entrée représente l’identifiant de l’organisation. Par exemple : `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. Cet identifiant se trouve dans le Admin Console .
   * PLC - Cette entrée permet d’accéder aux utilisateurs configurés pour une configuration de produit spécifique. Il peut être utilisé au format `Organization_Id-PLC`. Par exemple : `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. Les utilisateurs configurés pour Data Workbench à l’aide du PLC `DataworkbenchAdminUsers` accède à leurs serveurs.
   * Courrier électronique : cette entrée permet d’accéder à n’importe quel utilisateur individuel. Sa valeur doit être l’adresse électronique de l’utilisateur muni d’un profil d’approvisionnement. Par exemple : `1 = string: Email:kim@exampleorg.com`.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Les entrées sont sensibles à la casse. Vous devez vous assurer que les valeurs spécifiées pour O, PLC et Email sont exactement les mêmes que celles affichées dans le Admin Console.
   >    * Saisissez le nom commun tel qu’il apparaît sur le certificat.
   >    * N’utilisez pas la touche de tabulation pour générer un espace dans le [!DNL Access Control.cfg] (ou dans tout autre fichier de configuration d’un composant Adobe). Utilisez uniquement des espaces pour créer des espaces. Un caractère de tabulation empêche le système de lire correctement le fichier.


1. Enregistrez le fichier, puis fermez-le.
