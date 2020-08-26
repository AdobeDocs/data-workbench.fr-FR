---
description: Informations conceptuelles sur les calques d’images.
solution: Analytics
title: À propos des calques d’imagerie
topic: Data workbench
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
translation-type: tm+mt
source-git-commit: f4b37f50b115a1e1d2c9d000897a8fa47b03b233
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 5%

---


# À propos des calques d’imagerie{#about-imagery-layers}

Informations conceptuelles sur les calques d’images.

## Types de calques d’images {#section-891cbf61e8334690bd203a2bb9761b25}

Vous pouvez vue les types de calques d’images suivants dans le Data Workbench :

* **[!UICONTROL Terrain image layer]:** Ce type de couche affiche l&#39;imagerie du terrain de la Terre, sur laquelle les données géographiques peuvent être affichées. La visualisation du globe en est un exemple d&#39;une couche d&#39;image de terrain. See [Working with Terrain Image Layers](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL Element point layer]:** Ce type de calque affiche un point sur le globe pour chaque élément d’une dimension. See [Working with Element Point Layers](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd).

* **[!UICONTROL Vector layer]:** Ce type de calque affiche des données vectorielles (dessins au trait) sur le globe. See [Working with Vector Layers](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL Presentation layer]** Annotez et rendez les visualisations plus claires à l’aide d’une superposition de présentation. Ajoutez des légendes, des flèches, des images et des codes de couleur pour mettre en surbrillance vos données et les clarifier. Partagez-les ensuite avec d’autres personnes.

En Data Workbench, vous pouvez sélectionner les calques à afficher pour une tâche d’analyse particulière.

## Calques de profil de géographie {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

Le [!DNL Geography] profil fournit un ensemble de calques d’images par défaut, qui sont stockés dans le dossier Profiles\Geography\Maps folder within the Data Workbench server installation directory :

* **[!UICONTROL Blue Marble 2km]:** Cette couche d&#39;image de terrain crée une carte 3D du monde, qui s&#39;affiche lorsque vous ajoutez la visualisation du globe à un espace de travail. Lorsque ce calque n’est pas sélectionné, le globe n’est pas visible, mais les autres calques s’affichent toujours. Le [!DNL Blue Marble 2km.layer] fichier fait référence au [!DNL Blue Marble 2km.tsi] fichier.

* **[!UICONTROL Zip Points]:** Cette couche de points d’élément vous permet de mapper des emplacements dans votre jeu de données à l’aide d’un code postal des États-Unis. Le fichier [!DNL Zip Points.txt] de recherche (fourni par Adobe) contient une liste de tous les codes postaux des États-Unis et de la latitude et de la longitude de chaque code postal. Le [!DNL Zip Points.layer] fichier fait référence au [!DNL Zip Points.txt] fichier et au [!DNL Zipcode.dim] fichier et contient les paramètres de configuration nécessaires pour afficher les emplacements sur le globe. Chaque élément de la dimension Code postal ( [!DNL Zipcode.dim]) que vous définissez dans votre jeu de données est mappé sur le globe à l’aide de la latitude et de la longitude répertoriées pour ce code postal dans le fichier de [!DNL Zip Points.txt] recherche.

   Pour plus d&#39;informations sur la définition de dimensions, consultez le Guide *de configuration des jeux de* données.

* **[!UICONTROL Boundaries]:** Cette couche vectorielle fournit les principales frontières politiques mondiales, telles que les pays, ainsi que les limites des caractéristiques physiques naturelles de la Terre, comme les lacs et les îles. Le [!DNL Boundaries.layer] fichier fait référence à un ou plusieurs des fichiers [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec],  et .[!DNL US states.vec][!DNL world boundaries.vec]

* **[!UICONTROL IP Coordinates]:** Ce calque de points d’élément utilise des points dynamiques pour vous permettre de mapper des emplacements dans votre jeu de données à l’aide d’adresses IP. Le [!DNL IP Coordinates.layer] fichier fait référence à la dimension Coordonnées ( [!DNL Coordinates.dim]) et indique la mesure Visiteuse comme mesure à utiliser pour déterminer la taille des points du globe pour chaque coordonnée.

Votre [!UICONTROL NL Geography] profil ou d’autres profils de votre installation peuvent contenir d’autres couches d’images que l’Adobe a fournies ou que votre société a créées.

## Create a new layer {#section-b5313773316c4e0fa748f7376a8e7f0b}

Vous pouvez créer de nouveaux calques d’images en copiant le type de fichier de calques approprié inclus dans le [!DNL Geography] profil dans le dossier Profils\*nom du profil*\Maps, puis en renommant et en modifiant le fichier selon les besoins. Toutes les nouvelles couches doivent répondre aux exigences suivantes :

* Le [!DNL .layer] fichier doit respecter le format de l’un des types de calques pris en charge.
* Le [!DNL .layer] fichier doit référencer les fichiers de recherche et de dimension appropriés, si nécessaire.
* Le fichier de recherche référencé doit également être stocké dans le répertoire d’installation du serveur Data Workbench et son chemin d’accès doit être spécifié avec précision dans le [!DNL .layer] fichier.

Pour plus d&#39;informations sur le format et les paramètres de chaque type de fichier de calque et de ses fichiers associés, consultez la section de ce chapitre pour le type de calque approprié.
