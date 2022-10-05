---
description: Le répertoire des jeux de données contient des fichiers supplémentaires requis pour le fonctionnement du logiciel ou pour fournir des fonctionnalités supplémentaires à votre mise en oeuvre d’Adobe.
title: Autres fichiers
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---

# Autres fichiers{#other-files}

{{eol}}

Le répertoire des jeux de données contient des fichiers supplémentaires requis pour le fonctionnement du logiciel ou pour fournir des fonctionnalités supplémentaires à votre mise en oeuvre d’Adobe.

* **[!DNL Client.cfg:]** Le [!DNL Client.cfg] dans le répertoire du jeu de données pour la variable [!DNL Base] est requis pour le fonctionnement du logiciel. Ne supprimez ou ne modifiez aucun des paramètres de la variable [!DNL Client.cfg] fichier .

* **[!DNL Cluster.cfg:]** Le [!DNL Cluster.cfg] dans le répertoire du jeu de données pour la variable [!DNL Base] est requis pour le fonctionnement du logiciel. Dans le [!DNL Cluster.cfg] , vous ne devez modifier que le paramètre Normaliser le serveur si vous configurez un jeu de données à traiter sur une grappe de serveurs Data Workbench. Pour obtenir des instructions sur la modification du paramètre Normaliser le serveur, voir [Création d’un serveur de normalisation centralisé pour une grappe](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]et [!DNL Insight Transform Mode.cfg]:** Si vous utilisez la fonctionnalité de transformation, vous disposez de deux fichiers de configuration supplémentaires, Data Workbench. [!DNL Transform.cfg] et Data Workbench [!DNL TransformMode.cfg], dans le répertoire du jeu de données pour la variable [!DNL Transform] profile. Pour plus d’informations sur ces fichiers et leurs paramètres, voir [Fonctionnalité de transformation](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* Le **PAServer.cfg** fichier . Si vous souhaitez envoyer des tâches de mise en grappe Predictive Analytics aux serveurs Insight, vous devez configurer la variable [!DNL PAServer.cfg] pour gérer les envois de mise en grappe côté serveur.
Le profil personnalisé doit hériter de la variable [!DNL PAServer.cfg] à partir du profil Analyses prédictives ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Définir une *Principal Server* dans ce fichier et enregistrez la variable [!DNL PAServer.cfg] sur le site de mise en oeuvre.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
