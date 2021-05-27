---
description: Procédure d’installation des fichiers de recherche de géo-intelligence IP ou de géolocalisation IP.
title: Installation des fichiers Lookup de services de données
uuid: a3fe8a14-2c74-4105-bc5b-2298f0f4b61e
exl-id: b19904f4-ead0-4bed-a79f-864c78bc0e1d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 6%

---

# Installation des fichiers Lookup de services de données{#installing-the-data-service-lookup-files}

Procédure d’installation des fichiers de recherche de géo-intelligence IP ou de géolocalisation IP.

Le fichier de recherche (Lookups\*nom du profil*\*nom du fichier de données*) fourni avec le profil de service de données est un fichier binaire ( [!DNL .bin]) qui contient des données liées géographiquement en fonction de l’adresse IP. Vous devez remplacer ce fichier régulièrement pour vous assurer que vous disposez des données géographiques les plus récentes. Voir [Mise à jour des fichiers de service de données](../../../../home/c-geo-oview/c-wk-data-svcs/c-updt-data-svc-files.md#concept-2b3d11e4cb814fc09add5de58a87045c).

**Pour installer les fichiers de recherche de géolocalisation IP ou de géolocalisation IP**

>[!NOTE]
>
>Tous vos fichiers de données [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] doivent tenir dans la mémoire physique disponible de votre serveur Data Workbench.

1. Ouvrez le dossier Recherches à partir du fichier [!DNL .zip] que vous avez reçu d’Adobe.
1. Copiez le dossier IP Geo-intelligence ou IP Geo-location dans le dossier Lookups du répertoire d’installation de votre serveur Data Workbench (vous souhaitez obtenir un ...\Lookups\IP Geo-intelligence or a ...\Lookups\IP Geo-location folder on your data workbench server as shown in the following example. Les noms des autres dossiers du dossier Recherches peuvent différer de ceux affichés.

   ![Infos sur l’étape](assets/Geo_installLookups_dirIP.png)

   >[!NOTE]
   >
   >Régulièrement, Adobe vous envoie des fichiers contenant des fichiers de recherche [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] mis à jour. Lorsque vous recevez ces fichiers, vous devez les charger sur votre serveur Data Workbench tel que dirigé par Adobe. Pour obtenir des instructions, reportez-vous à la section suivante.
