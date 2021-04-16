---
description: Le répertoire des jeux de données contient des fichiers supplémentaires qui sont nécessaires au fonctionnement du logiciel ou qui fournissent des fonctionnalités supplémentaires pour l'implémentation de votre Adobe.
title: Autres fichiers
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 1%

---

# Autres fichiers{#other-files}

Le répertoire des jeux de données contient des fichiers supplémentaires qui sont nécessaires au fonctionnement du logiciel ou qui fournissent des fonctionnalités supplémentaires pour l&#39;implémentation de votre Adobe.

* **[!DNL Client.cfg:]** Le  [!DNL Client.cfg] fichier situé dans le répertoire Dataset du  [!DNL Base] profil est nécessaire au fonctionnement du logiciel. Ne supprimez ou ne modifiez aucun des paramètres du fichier [!DNL Client.cfg].

* **[!DNL Cluster.cfg:]** Le  [!DNL Cluster.cfg] fichier situé dans le répertoire Dataset du  [!DNL Base] profil est nécessaire au fonctionnement du logiciel. Dans le fichier [!DNL Cluster.cfg], vous ne devez modifier que le paramètre Normaliser le serveur si vous configurez un jeu de données à traiter sur une grappe de serveurs Outils de données. Pour obtenir des instructions sur la modification du paramètre Normaliser le serveur, voir [Création d&#39;un serveur de normalisation centralisée pour une grappe](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]et  [!DNL Insight Transform Mode.cfg]:** Si vous utilisez la fonctionnalité de transformation, vous avez deux fichiers de configuration supplémentaires, les outils de données  [!DNL Transform.cfg] et les outils de données  [!DNL TransformMode.cfg], dans le répertoire Dataset du  [!DNL Transform] profil. Pour plus d’informations sur ces fichiers et leurs paramètres, voir [Fonctionnalité de transformation](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* Le fichier **PAServer.cfg**. Si vous souhaitez envoyer des tâches de mise en grappe Predictive Analytics aux serveurs Insight, vous devez configurer le fichier [!DNL PAServer.cfg] pour gérer les envois de mise en grappe côté serveur.
Le profil personnalisé doit hériter de [!DNL PAServer.cfg] du profil Analyses prédictives ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Définissez un *Principal Server* dans ce fichier et enregistrez [!DNL PAServer.cfg] sur le site d&#39;implémentation.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
