---
description: Le fichier Access Control.cfg gère l’accès à certaines fonctionnalités d’Insight Server.
solution: Insight
title: Mise à jour du fichier de contrôle d'accès
uuid: f73651e5-6a8b-45fc-8f36-6751304dc53c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mise à jour du fichier de contrôle d&#39;accès{#updating-the-access-control-file}

Le fichier Access Control.cfg gère l’accès à certaines fonctionnalités d’Insight Server.

Elle définit des entités appelées AccessGroups. Un groupe AccessGroup identifie un groupe d&#39;utilisateurs autorisés à utiliser certaines fonctionnalités du serveur.

Avant de pouvoir vous connecter [!DNL Insight Server] à [!DNL Insight], vous devez mettre à jour le groupe d’accès Administrateurs afin d’inclure l’une des [!DNL Insight] licences qu’Adobe a délivrées à votre entreprise. Ce AccessGroup identifie les utilisateurs autorisés à exécuter des fonctions d&#39;administration par le biais de [!DNL Insight].

La procédure suivante décrit l’ajout d’une licence à l’élément Administration AccessGroup. Pour terminer cette tâche, vous devez déterminer quelle [!DNL Insight] licence possède des privilèges d’administration pour votre entreprise. (Pour la configuration et la configuration initiales, accorder des privilèges d’administration à une seule licence suffit. Vous pourrez ultérieurement accorder des privilèges d’administration à d’autres licences.) Vous devez également connaître le &quot;nom commun&quot; attribué à cette licence. Pour obtenir cette valeur, vous pouvez consulter les certificats de licence de votre compte à l’adresse [https://aap.adobe.com](https://aap.adobe.com).

L’objectif de cette procédure est simplement d’identifier une copie sous licence de [!DNL Insight] laquelle vous pouvez utiliser pour configurer et configurer initialement [!DNL Insight Server]. Une fois que vous avez identifié cette licence, vous pouvez effectuer toutes les configurations de serveur suivantes (y compris une configuration AccessGroup supplémentaire) à l&#39;aide de la copie sous licence de [!DNL Insight]. Pour plus d&#39;informations sur le contrôle de l&#39;accès au serveur à l&#39;aide de AccessGroups, consultez [Configuration du contrôle](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)d&#39;accès.

**Pour mettre à jour le fichier de contrôle d’accès**

1. Accédez au [!DNL Access Control] dossier du répertoire dans lequel vous avez installé [!DNL Insight Server].

   Exemple : [!DNL C:\Adobe\Server\Access Control]

1. Ouvrez le [!DNL Access Control.cfg] fichier dans un éditeur de texte tel que le Bloc-notes.
1. Localisez l&#39;entrée CN dans le groupe d&#39;accès Administrateurs et remplacez la valeur existante de cette entrée par le nom commun qui identifie le [!DNL Insight] que vous utiliserez pour configurer et administrer initialement [!DNL Insight Server]. Le fragment de fichier suivant illustre l’emplacement où vous insérez le nom commun dans le [!DNL Access Control.cfg] fichier.

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

   Si vous utilisez une authentification basée sur les informations d’identification, quelques entrées supplémentaires seront disponibles pour la configuration. Ces entrées sont les suivantes :

   * O (ID d’organisation) : Cette entrée représente l’ID de l’organisation. Par exemple : `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. Cet ID se trouve dans la console d’administration.
   * PLC - Cette entrée permet d&#39;accéder aux utilisateurs configurés pour une configuration de produit spécifique. Il peut être utilisé dans le format `Organization_Id-PLC`. Par exemple : `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. Les utilisateurs configurés pour les outils de données à l’aide du PLC `DataworkbenchAdminUsers` obtiendront un accès sur leurs serveurs.
   * E-mail : cette entrée permet d&#39;accéder à n&#39;importe quel utilisateur individuel. Sa valeur doit correspondre à l’adresse électronique de l’utilisateur configuré. Par exemple : `1 = string: Email:kim@exampleorg.com`.
   >[!NOTE]
   >
   >
   >    
   >    
   >    * Les entrées sont sensibles à la casse. Vous devez vous assurer que les valeurs spécifiées pour O, PLC et Email sont exactement les mêmes que celles affichées dans la console d’administration.
   >    * Tapez le nom commun tel qu’il apparaît sur le certificat.
   >    * N’utilisez pas la touche de tabulation pour générer des espaces blancs dans le [!DNL Access Control.cfg] fichier (ou dans tout autre fichier de configuration d’un composant Adobe). Utilisez uniquement des espaces pour créer des espaces blancs. Un caractère de tabulation empêche le système de lire correctement le fichier.


1. Enregistrez et fermez le fichier.

