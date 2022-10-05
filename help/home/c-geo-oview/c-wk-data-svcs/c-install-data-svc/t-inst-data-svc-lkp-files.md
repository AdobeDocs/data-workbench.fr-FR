---
description: Procédure d’installation des fichiers de recherche de géo-intelligence IP ou de géolocalisation IP.
title: Installation des fichiers Lookup de services de données
uuid: a3fe8a14-2c74-4105-bc5b-2298f0f4b61e
exl-id: b19904f4-ead0-4bed-a79f-864c78bc0e1d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 6%

---

# Installation des fichiers Lookup de services de données{#installing-the-data-service-lookup-files}

{{eol}}

Procédure d’installation des fichiers de recherche de géo-intelligence IP ou de géolocalisation IP.

Le fichier de recherche (Lookups\*nom du profil*\*nom du fichier de données*) fourni avec le profil du service de données est un fichier binaire ( [!DNL .bin]) qui contient des données géographiquement liées en fonction de l’adresse IP. Vous devez remplacer ce fichier régulièrement pour vous assurer que vous disposez des données géographiques les plus récentes. Voir [Mise à jour des fichiers de service de données](../../../../home/c-geo-oview/c-wk-data-svcs/c-updt-data-svc-files.md#concept-2b3d11e4cb814fc09add5de58a87045c).

**Pour installer les fichiers de recherche de géolocalisation IP ou de géolocalisation IP**

>[!NOTE]
>
>Tous vos [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] les fichiers de données doivent tenir dans la mémoire physique disponible de votre serveur Data Workbench.

1. Ouvrez le dossier Recherches à partir du [!DNL .zip] fichier que vous avez reçu d’Adobe.
1. Copiez le dossier IP Geo-intelligence ou IP Geo-location dans le dossier Lookups du répertoire d’installation de votre serveur Data Workbench (vous souhaitez obtenir un ...\Recherches\IP Géo-intelligence ou ...\Lookups\IP Géolocalisation sur votre serveur Data Workbench, comme illustré dans l’exemple suivant. Les noms des autres dossiers du dossier Recherches peuvent différer de ceux affichés.

   ![Infos sur l’étape](assets/Geo_installLookups_dirIP.png)

   >[!NOTE]
   >
   >Régulièrement, Adobe vous envoie les fichiers contenant des mises à jour [!DNL IP Geo-intelligence] ou [!DNL IP Geo-location] fichiers de recherche. Lorsque vous recevez ces fichiers, vous devez les charger sur votre serveur Data Workbench tel que dirigé par Adobe. Pour obtenir des instructions, reportez-vous à la section suivante.
