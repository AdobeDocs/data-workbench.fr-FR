---
description: Informations conceptuelles sur les calques d’imagerie.
title: À propos des calques d’imagerie
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
exl-id: c6d30747-70d2-4489-ad64-fd131e76a7a2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 5%

---

# À propos des calques d’imagerie{#about-imagery-layers}

Informations conceptuelles sur les calques d’imagerie.

## Types de calques d’imagerie {#section-891cbf61e8334690bd203a2bb9761b25}

Vous pouvez afficher les types de calques d’imagerie suivants en Data Workbench :

* **[!UICONTROL Terrain image layer]:** Ce type de couche affiche l’imagerie du terrain de la Terre, sur laquelle les données géographiques peuvent être affichées. La visualisation du globe dans est un exemple de calque d’image du terrain. Voir [Utilisation des calques d’image du terrain](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL Element point layer]:** ce type de calque affiche un point sur le globe pour chaque élément d’une dimension. Voir [Utilisation des calques de point d’élément](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd).

* **[!UICONTROL Vector layer]:** ce type de couche affiche des données vectorielles (dessins au trait) sur la planète. Voir [Utilisation des calques vectoriels](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL Presentation layer]** Annotez et rendez les visualisations plus claires à l’aide d’une superposition de présentation. Ajoutez des légendes, des flèches, des images et des codes de couleur pour mettre en surbrillance vos données et les clarifier. Partagez-les ensuite avec d’autres personnes.

Dans Data Workbench, vous pouvez sélectionner les calques à afficher pour une tâche d’analyse particulière.

## Calques de profil de géographie {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

Le profil [!DNL Geography] vous fournit un ensemble de calques d’imagerie par défaut, stockés dans le dossier Profiles\Geography\Maps folder within the Data Workbench server installation directory :

* **[!UICONTROL Blue Marble 2km]:** Cette couche d’image du terrain crée une carte 3D du monde, qui s’affiche lorsque vous ajoutez la visualisation du globe à un espace de travail. Lorsque ce calque n’est pas sélectionné, le globe n’est pas visible, mais les autres calques s’affichent toujours. Le fichier [!DNL Blue Marble 2km.layer] référence le fichier [!DNL Blue Marble 2km.tsi].

* **[!UICONTROL Zip Points]:** Cette couche de point d’élément vous permet de mapper des emplacements dans votre jeu de données à l’aide d’un code postal des États-Unis. Le fichier de recherche [!DNL Zip Points.txt] (fourni par Adobe) contient une liste de tous les codes postaux des États-Unis, ainsi que la latitude et la longitude de chaque code postal. Le fichier [!DNL Zip Points.layer] référence le fichier [!DNL Zip Points.txt] et le fichier [!DNL Zipcode.dim] et contient les paramètres de configuration nécessaires pour afficher les emplacements sur le globe. Chaque élément de la dimension Code postal ( [!DNL Zipcode.dim]) que vous définissez dans votre jeu de données est mappé sur le globe à l’aide de la latitude et de la longitude répertoriées pour ce code postal dans le fichier de recherche [!DNL Zip Points.txt].

   Pour plus d’informations sur la définition de dimensions, consultez le *Guide de configuration des jeux de données*.

* **[!UICONTROL Boundaries]:** Cette couche vectorielle fournit les principales frontières politiques mondiales, comme les pays, ainsi que les limites des caractéristiques physiques naturelles de la Terre, comme les lacs et les îles. Le fichier [!DNL Boundaries.layer] fait référence à un ou plusieurs des fichiers [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec] et [!DNL world boundaries.vec].

* **[!UICONTROL IP Coordinates]:** cette couche de point d’élément utilise des points dynamiques pour vous permettre de mapper des emplacements dans votre jeu de données à l’aide d’adresses IP. Le fichier [!DNL IP Coordinates.layer] fait référence à la dimension Coordonnées ( [!DNL Coordinates.dim]) et spécifie la mesure Visiteurs comme mesure à utiliser pour déterminer la taille des points sur la globe pour chaque coordonnée.

Votre profil [!UICONTROL NL Geography] ou d’autres profils de votre installation peuvent contenir des calques d’imagerie supplémentaires qui s’Adobe fournis pour votre entreprise créée.

## Créer un nouveau calque {#section-b5313773316c4e0fa748f7376a8e7f0b}

Vous pouvez créer de nouveaux calques d’imagerie en copiant le type de fichier de calque approprié inclus dans le profil [!DNL Geography] dans n’importe quel dossier Profils\*nom du profil*\Mappages , puis en renommant et en modifiant le fichier selon les besoins. Toutes les nouvelles couches doivent répondre aux exigences suivantes :

* Le fichier [!DNL .layer] doit respecter le format de l’un des types de calques pris en charge.
* Si nécessaire, le fichier [!DNL .layer] doit faire référence aux fichiers de recherche et de dimension appropriés.
* Le fichier de recherche référencé doit également être stocké dans le répertoire d’installation du serveur Data Workbench et son chemin d’accès doit être spécifié avec précision dans le fichier [!DNL .layer].

Pour plus d’informations sur le format et les paramètres de chaque type de fichier de calque et des fichiers associés, consultez la section de ce chapitre pour le type de calque approprié.
