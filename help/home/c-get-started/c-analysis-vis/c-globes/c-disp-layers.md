---
description: Le profil Geography stocke une collection de calques et de fichiers d’imagerie.
title: Afficher les calques
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
exl-id: 12ec913f-c7e5-49b5-8792-db0881cb5cfe
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 1%

---

# Afficher les calques{#display-layers}

{{eol}}

Le profil Geography stocke une collection de calques et de fichiers d’imagerie.

Lorsque vous affichez un globe, vous pouvez sélectionner les calques disponibles à afficher pour une tâche d’analyse particulière :

* **Marbre bleu 2km :** Ce calque affiche le globe. Lorsque ce calque n’est pas sélectionné, le globe n’est pas visible.
* **Coordonnées IP :** Cette couche de point d’élément affiche la latitude et la longitude des emplacements dans votre jeu de données en fonction des adresses IP des visiteurs.
* **Zip Points :** Cette couche affiche la latitude et la longitude des emplacements dans votre jeu de données en fonction d’une liste de codes postaux des États-Unis fournis par Adobe. Le [!DNL Zip Points.txt] Le fichier de recherche contient le code postal, la latitude et la longitude des données à afficher, tandis que la variable [!DNL Zip Points.layer] contient les paramètres de configuration nécessaires pour afficher ces données sur le globe. Ces deux fichiers sont stockés dans le dossier Profils\Geography\Maps du répertoire d’installation du serveur Data Workbench.

* ***Autres noms de calque disponibles :*** Chaque nom de calque représente [!DNL .layer] stocké dans le dossier Profils\Geography\Maps , Profils\IP Geo-location\Maps ou dans le dossier Profils\IP Geo-intelligence\Maps du répertoire d’installation du serveur Insight.

>[!NOTE]
>
>Pour disposer du profil Géolocalisation IP ou Géolocalisation IP, vous devez vous abonner respectivement au service de géolocalisation IP ou Géolocalisation IP.

Pour contrôler l’ordre d’affichage des calques, vous pouvez utiliser une [!DNL order.txt] fichier . Voir [Personnalisation des menus à l’aide des fichiers Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

**Pour basculer des calques sur un globe**

* Cliquez avec le bouton droit dans la visualisation, puis cliquez sur le nom du calque de votre choix. Un X à gauche du calque indique que le calque est visible.
