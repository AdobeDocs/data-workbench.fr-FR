---
description: Le profil Géographie stocke une collection de calques et de fichiers d’images.
title: Afficher les calques
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
exl-id: 12ec913f-c7e5-49b5-8792-db0881cb5cfe
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 1%

---

# Afficher les calques{#display-layers}

Le profil Géographie stocke une collection de calques et de fichiers d’images.

Lorsque vous affichez un globe, vous pouvez sélectionner les calques disponibles à afficher pour une tâche d’analyse particulière :

* **Marbre bleu 2km :** Cette couche affiche le globe. Lorsque ce calque n’est pas sélectionné, le globe n’est pas visible.
* **Coordonnées IP :** cette couche de points d’élément affiche la latitude et la longitude des emplacements dans votre jeu de données en fonction des adresses IP du visiteur.
* **Points postaux :** ce calque affiche la latitude et la longitude des emplacements dans votre jeu de données en fonction d’une liste de codes postaux des États-Unis fournis par Adobe. Le fichier de recherche [!DNL Zip Points.txt] contient les données de code postal, de latitude et de longitude à afficher, tandis que le fichier [!DNL Zip Points.layer] contient les paramètres de configuration nécessaires pour afficher ces données sur le globe. Ces deux fichiers sont stockés dans le dossier Profiles\Geography\Maps folder within the Data Workbench server installation directory.

* ***Autres noms de calque disponibles :*** Chaque nom de calque représente un  [!DNL .layer] fichier stocké dans le dossier Profiles\Geography\Maps folder, Profils\IP Geo-location\Maps ou dans le dossier Profils\IP Geo-intelligence\Maps du répertoire d’installation d’Insight Server.

>[!NOTE]
>
>Pour disposer du profil de géolocalisation IP ou de géointelligence IP, vous devez vous abonner respectivement au service de données de géolocalisation IP ou de géointelligence IP.

Pour contrôler l’ordre d’affichage des calques, vous pouvez utiliser un fichier [!DNL order.txt]. Voir [Personnalisation des menus à l’aide des fichiers Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

**Pour faire basculer des calques sur un globe**

* Cliquez avec le bouton droit de la souris dans la visualisation et cliquez sur le nom du calque de votre choix. Un X à gauche du calque indique que le calque est visible.
