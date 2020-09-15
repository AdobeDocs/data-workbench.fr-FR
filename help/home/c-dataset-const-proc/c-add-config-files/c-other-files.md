---
description: Le répertoire des jeux de données contient des fichiers supplémentaires qui sont nécessaires au fonctionnement du logiciel ou qui fournissent des fonctionnalités supplémentaires pour l'implémentation de votre Adobe.
solution: Analytics
title: Autres fichiers
topic: Data workbench
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
translation-type: tm+mt
source-git-commit: 98452ba81d71db65c75e3d07712eefa18c003f53
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 1%

---


# Autres fichiers{#other-files}

Le répertoire des jeux de données contient des fichiers supplémentaires qui sont nécessaires au fonctionnement du logiciel ou qui fournissent des fonctionnalités supplémentaires pour l&#39;implémentation de votre Adobe.

* **[!DNL Client.cfg:]** Le [!DNL Client.cfg] fichier situé dans le répertoire Dataset du [!DNL Base] profil est nécessaire au fonctionnement du logiciel. Ne supprimez ou ne modifiez aucun des paramètres du [!DNL Client.cfg] fichier.

* **[!DNL Cluster.cfg:]** Le [!DNL Cluster.cfg] fichier situé dans le répertoire Dataset du [!DNL Base] profil est nécessaire au fonctionnement du logiciel. Dans le [!DNL Cluster.cfg] fichier, vous ne devez modifier que le paramètre Normaliser le serveur si vous configurez un jeu de données à traiter sur une grappe de serveurs Outils de données. Pour obtenir des instructions sur la modification du paramètre Normaliser le serveur, voir [Création d&#39;un serveur de normalisation centralisée pour une grappe](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]et[!DNL Insight Transform Mode.cfg]:** Si vous utilisez la fonctionnalité de transformation, vous disposez de deux fichiers de configuration supplémentaires, les outils de données [!DNL Transform.cfg] et les outils de données [!DNL TransformMode.cfg], dans le répertoire Dataset du [!DNL Transform] profil. Pour plus d’informations sur ces fichiers et leurs paramètres, voir Fonctionnalité [de](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html)transformation.

* Fichier **PAServer.cfg** . Si vous souhaitez envoyer des tâches de mise en grappe Predictive Analytics aux serveurs Insight, vous devez configurer le [!DNL PAServer.cfg] fichier pour gérer les envois de mise en grappe côté serveur.
Le profil personnalisé doit hériter de la valeur [!DNL PAServer.cfg] du profil Analyses prédictives ( [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Définissez un serveur *de* Principal dans ce fichier et enregistrez-le [!DNL PAServer.cfg] sur le site de mise en oeuvre.
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```

