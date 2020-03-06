---
description: Le profil Géographie stocke une collection de calques et de fichiers d’imagerie.
solution: Analytics
title: Afficher les calques
topic: Data workbench
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Afficher les calques{#display-layers}

Le profil Géographie stocke une collection de calques et de fichiers d’imagerie.

Lorsque vous affichez un globe, vous pouvez sélectionner les calques disponibles à afficher pour une tâche d’analyse particulière :

* **Marbre bleu 2km :** Ce calque affiche le globe. Lorsque ce calque n’est pas sélectionné, le globe n’est pas visible.
* **Coordonnées IP :** Ce calque de point d’élément affiche la latitude et la longitude des emplacements dans votre jeu de données en fonction des adresses IP des visiteurs.
* **Points postaux :** Ce calque affiche la latitude et la longitude des emplacements dans votre jeu de données en fonction d’une liste de codes postaux des États-Unis fournis par Adobe. Le fichier de [!DNL Zip Points.txt] recherche contient les données de code postal, de latitude et de longitude à afficher, tandis que le [!DNL Zip Points.layer] fichier contient les paramètres de configuration nécessaires pour afficher ces données sur le globe. Ces deux fichiers sont stockés dans le dossier Profiles\Geography\Maps folder within the Data Workbench server installation directory.

* ***Autres noms de calque disponibles :*** Chaque nom de calque représente un [!DNL .layer] fichier stocké dans le dossier Profiles\Geography\Maps folder, Profils\IP Geo-location\Maps ou Profils\IP Geo-intelligence\Maps dans le répertoire d’installation du serveur Insight.

>[!NOTE]
>
>Pour disposer du profil de géolocalisation IP ou de géointelligence IP, vous devez vous abonner respectivement au service de données de géolocalisation IP ou au service de géointelligence IP.

Pour contrôler l’ordre d’affichage des calques, vous pouvez utiliser un [!DNL order.txt] fichier. Voir [Personnalisation des menus à l’aide des fichiers](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.

**Pour activer/désactiver des calques dans un globe**

* Cliquez avec le bouton droit de la souris dans la visualisation et cliquez sur le nom du calque souhaité. Un X à gauche du calque indique que le calque est visible.

