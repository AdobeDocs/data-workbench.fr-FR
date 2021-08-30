---
description: Le répertoire des jeux de données contient des fichiers supplémentaires requis pour le fonctionnement du logiciel ou pour fournir des fonctionnalités supplémentaires à votre mise en oeuvre d’Adobe.
title: Autres fichiers
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---

# Autres fichiers{#other-files}

Le répertoire des jeux de données contient des fichiers supplémentaires requis pour le fonctionnement du logiciel ou pour fournir des fonctionnalités supplémentaires à votre mise en oeuvre d’Adobe.

* **[!DNL Client.cfg:]** Le  [!DNL Client.cfg] fichier du répertoire du jeu de données du  [!DNL Base] profil est requis pour le fonctionnement du logiciel. Ne supprimez ou ne modifiez aucun des paramètres du fichier [!DNL Client.cfg].

* **[!DNL Cluster.cfg:]** Le  [!DNL Cluster.cfg] fichier du répertoire du jeu de données du  [!DNL Base] profil est requis pour le fonctionnement du logiciel. Dans le fichier [!DNL Cluster.cfg] , vous ne devez modifier que le paramètre Normaliser le serveur si vous configurez un jeu de données à traiter sur une grappe de serveurs Data Workbench. Pour obtenir des instructions sur la modification du paramètre Normaliser le serveur, voir [Création d’un serveur de normalisation centralisé pour une grappe](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]et  [!DNL Insight Transform Mode.cfg] :** si vous utilisez la fonctionnalité de transformation, vous disposez de deux fichiers de configuration supplémentaires, Data Workbench  [!DNL Transform.cfg] et Data Workbench  [!DNL TransformMode.cfg], dans le répertoire du jeu de données pour le  [!DNL Transform] profil. Pour plus d’informations sur ces fichiers et leurs paramètres, voir [Fonctionnalité de transformation](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* Le fichier **PAServer.cfg**. Si vous souhaitez envoyer des tâches de mise en grappe Predictive Analytics aux serveurs Insight, vous devez configurer le fichier [!DNL PAServer.cfg] pour gérer les envois de mise en grappe côté serveur.
Le profil personnalisé doit hériter de [!DNL PAServer.cfg] du profil Analytics prédictif ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Définissez un *serveur de Principal* dans ce fichier et enregistrez le [!DNL PAServer.cfg] sur le site de mise en oeuvre.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
