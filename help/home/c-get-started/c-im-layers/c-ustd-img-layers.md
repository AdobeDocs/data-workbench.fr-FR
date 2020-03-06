---
description: Informations conceptuelles sur les calques d’imagerie.
solution: Analytics
title: A propos des calques d’image
topic: Data workbench
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# A propos des calques d’image{#about-imagery-layers}

Informations conceptuelles sur les calques d’imagerie.

## Types de calques d’imagerie {#section-891cbf61e8334690bd203a2bb9761b25}

Vous pouvez afficher les types de calques d’imagerie suivants dans les Outils de données :

* **[!UICONTROL Terrain image layer]:**Ce type de couche affiche l&#39;imagerie du terrain de la Terre, sur laquelle les données géographiques peuvent être affichées. La visualisation du globe en est un exemple de couche d&#39;image du terrain. Voir[Utilisation des calques d’image Terrain](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL Element point layer]:**Ce type de calque affiche un point sur le globe pour chaque élément d’une dimension. Voir[Utilisation de calques](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd)de point d’élément.

* **[!UICONTROL Vector layer]:**Ce type de calque affiche des données vectorielles (dessins au trait) sur le globe. Voir[Utilisation de calques](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9)vectoriels.

* **[!UICONTROL Presentation layer]** Annotez et rendez les visualisations plus claires à l’aide d’une superposition de présentation. Ajoutez des légendes, des flèches, des images et des codes de couleur pour mettre en surbrillance vos données et les clarifier. Partagez-les ensuite avec d’autres personnes.

Dans Outils de données, vous pouvez sélectionner les calques à afficher pour une tâche d’analyse particulière.

## Calques de profil de géographie {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

Le [!DNL Geography] profil fournit un ensemble de calques d’images par défaut, qui sont stockés dans le dossier Profiles\Geography\Maps folder within the Data Workbench server installation directory :

* **[!UICONTROL Blue Marble 2km]:**Cette couche d&#39;image de terrain crée une carte 3D du monde, ce qui s&#39;affiche lorsque vous ajoutez la visualisation du globe à un espace de travail. Lorsque ce calque n’est pas sélectionné, le globe n’est pas visible, mais les autres calques s’affichent toujours. Le[!DNL Blue Marble 2km.layer]fichier fait référence au[!DNL Blue Marble 2km.tsi]fichier.

* **[!UICONTROL Zip Points]:**Ce calque de point d’élément vous permet de mapper des emplacements dans votre jeu de données à l’aide d’un code postal des États-Unis. Le fichier[!DNL Zip Points.txt]de recherche (fourni par Adobe) contient une liste de tous les codes postaux des États-Unis et de la latitude et de la longitude de chaque code postal. Le[!DNL Zip Points.layer]fichier fait référence au[!DNL Zip Points.txt]fichier et au[!DNL Zipcode.dim]fichier et contient les paramètres de configuration nécessaires pour afficher les emplacements sur le globe. Chaque élément de la dimension Code postal ([!DNL Zipcode.dim]) que vous définissez dans votre jeu de données est mappé sur le globe à l’aide de la latitude et de la longitude répertoriées pour ce code postal dans le fichier de[!DNL Zip Points.txt]recherche.

   Pour plus d’informations sur la définition des dimensions, voir le Guide *de configuration des jeux de* données.

* **[!UICONTROL Boundaries]:**Cette couche vectorielle fournit les principales frontières politiques mondiales, comme les pays, ainsi que les limites des caractéristiques physiques naturelles de la Terre, comme les lacs et les îles. Le[!DNL Boundaries.layer]fichier fait référence à un ou plusieurs des[!DNL mwcoast.vec],[!DNL mwisland.vec],[!DNL mwlake.vec],[!DNL mwnation.vec],[!DNL mwriver.vec],[!DNL mwstate.vec],  et  fichiers.[!DNL US states.vec][!DNL world boundaries.vec]

* **[!UICONTROL IP Coordinates]:**Ce calque de points d’élément utilise des points dynamiques pour vous permettre de mapper des emplacements dans votre jeu de données à l’aide d’adresses IP. Le[!DNL IP Coordinates.layer]fichier fait référence à la dimension Coordonnées ([!DNL Coordinates.dim]) et indique la mesure Visiteurs comme mesure à utiliser pour déterminer la taille des points du globe pour chaque coordonnée.

Votre profil de [!UICONTROLNL géographie] ou d’autres profils dans votre installation peuvent contenir des couches d’images supplémentaires fournies par Adobe ou créées par votre entreprise.

## Create a new layer {#section-b5313773316c4e0fa748f7376a8e7f0b}

Vous pouvez créer des calques d’images en copiant le type de fichier de calque approprié inclus dans le [!DNL Geography] profil dans n’importe quel dossier Profils\*nom du profil*\Mappages, puis en renommant et en modifiant le fichier selon les besoins. Tous les nouveaux calques doivent répondre aux exigences suivantes :

* Le [!DNL .layer] fichier doit respecter le format de l’un des types de calques pris en charge.
* Le [!DNL .layer] fichier doit faire référence aux fichiers de recherche et de dimension appropriés, si nécessaire.
* Le fichier de recherche référencé doit également être stocké dans le répertoire d’installation du serveur Outils de données et son chemin d’accès doit être spécifié avec précision dans le [!DNL .layer] fichier.

Pour plus d’informations sur le format et les paramètres de chaque type de fichier de calque et des fichiers associés, voir la section de ce chapitre pour le type de calque approprié.
