---
description: Informations sur l’installation d’un service de données sur un serveur Data Workbench.
title: Installation d’un service de données sur un serveur Data Workbench
uuid: afe8e259-7fef-4327-9afc-18f36a1934db
exl-id: 414e93b7-4e9c-4c84-8fba-8052939240c5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 7%

---

# Installation d’un service de données sur un serveur Data Workbench{#installing-a-data-service-on-a-data-workbench-server}

Informations sur l’installation d’un service de données sur un serveur Data Workbench.

Si vous utilisez le service de données de géointelligence IP ou le service de données de géolocalisation IP, vous devez installer le profil [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] et les fichiers de recherche associés sur votre serveur Data Workbench. Vous devez suivre les procédures suivantes après avoir installé le profil Data Workbench [!DNL Geography]. Voir [Installation de Data Workbench Geography](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md). Si vous n’avez pas installé Data Workbench, suivez les instructions du *Guide de l’utilisateur du Data Workbench* avant de continuer.

>[!NOTE]
>
>Pour installer les fichiers de service de données, vous devez avoir accès aux fichiers sur le serveur Data Workbench.

Adobe distribue les services de géointelligence IP et de géolocalisation IP sous la forme de fichiers [!DNL .zip]. Chaque fichier [!DNL .zip] contient deux dossiers : Recherches et profils. Pour installer un service de données sur le serveur Data Workbench, procédez comme suit :

* Installez le profil du service de données. Voir [Installation du profil de service de données](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/c-inst-data-svc-prof.md).
* Installez les recherches de service de données. Voir [Installation des fichiers de recherche de services de données](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/t-inst-data-svc-lkp-files.md).

Vous devez installer le profil de service de données et les fichiers de recherche sur l’ordinateur serveur Data Workbench sur lequel vous traitez et exécutez votre profil de jeu de données. Si vous exécutez une grappe de serveurs Data Workbench, vous devez installer les fichiers sur le serveur maître. Pour plus d’informations sur les profils de jeux de données, consultez le *Guide de configuration des jeux de données*.
