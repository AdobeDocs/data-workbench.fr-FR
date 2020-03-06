---
description: Le répertoire Jeu de données contient des fichiers supplémentaires requis pour le fonctionnement du logiciel ou pour fournir des fonctionnalités supplémentaires pour votre implémentation Adobe.
solution: Analytics
title: Autres fichiers
topic: Data workbench
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Autres fichiers{#other-files}

Le répertoire Jeu de données contient des fichiers supplémentaires requis pour le fonctionnement du logiciel ou pour fournir des fonctionnalités supplémentaires pour votre implémentation Adobe.

* **[!DNL Client.cfg:]** Le [!DNL Client.cfg] fichier du répertoire des jeux de données pour le [!DNL Base] profil est requis pour le fonctionnement du logiciel. Ne supprimez ni ne modifiez aucun des paramètres du [!DNL Client.cfg] fichier.

* **[!DNL Cluster.cfg:]** Le [!DNL Cluster.cfg] fichier du répertoire des jeux de données pour le [!DNL Base] profil est requis pour le fonctionnement du logiciel. Dans le [!DNL Cluster.cfg] fichier, vous ne devez modifier que le paramètre Normaliser le serveur si vous configurez un jeu de données à traiter sur une grappe de serveurs Outils de données. Pour plus d’informations sur la modification du paramètre Normaliser le serveur, voir [Création d’un serveur de normalisation centralisée pour une grappe](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]et[!DNL Insight Transform Mode.cfg]:**Si vous utilisez la fonctionnalité de transformation, vous disposez de deux fichiers de configuration supplémentaires, les outils de données[!DNL Transform.cfg]et les outils de données[!DNL TransformMode.cfg], dans le répertoire Jeu de données du[!DNL Transform]profil. Pour plus d’informations sur ces fichiers et leurs paramètres, voir Fonctionnalité[de](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html)transformation.

* Fichier **PAServer.cfg** . Si vous souhaitez envoyer des tâches de mise en grappe Predictive Analytics aux serveurs Insight, vous devez configurer le [!DNL PAServer.cfg] fichier pour gérer les envois de mise en grappe côté serveur.
Le profil personnalisé doit hériter du profil Analyses prédictives ( [!DNL PAServer.cfg] [!DNL Server\Profiles\Predictive Analytics\Dataset]).

   >[!IMPORTANT]
   >
   >Définissez un serveur *maître* dans ce fichier et enregistrez le serveur [!DNL PAServer.cfg] sur le site d’implémentation.   >
   >
   >
   ```>
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```  >
   >



