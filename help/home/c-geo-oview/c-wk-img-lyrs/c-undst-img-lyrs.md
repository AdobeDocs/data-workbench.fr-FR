---
description: Informations conceptuelles sur les calques de profil de la zone géographique, les types de calques d’imagerie et la création de nouveaux calques.
solution: Analytics
title: Présentation des calques d’image
topic: Data workbench
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Présentation des calques d’image{#understanding-imagery-layers}

Informations conceptuelles sur les calques de profil de la zone géographique, les types de calques d’imagerie et la création de nouveaux calques.

## Types de calques d’image {#section-ce25364651a04cd1b83f9ac7c231fa41}

Les outils de données [!DNL Geography] vous permettent d’afficher les types suivants de calques d’images dans les outils de données :

* **Calque d’image de terrain :** Ce type de couche affiche l&#39;imagerie du terrain de la Terre, sur laquelle les données géographiques peuvent être affichées. La visualisation du globe dans les outils de données est un exemple de couche d’image de terrain. Voir [Utilisation des calques d’image Terrain](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **Calque de point d’élément :** Ce type de calque affiche un point sur le globe pour chaque élément d’une dimension. Voir [Utilisation de calques](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9)de point d’élément.

* **Calque vectoriel :** Ce type de calque affiche des données vectorielles (dessins au trait) sur le globe. Voir [Utilisation de calques](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620)vectoriels.

Dans les outils de données, vous pouvez sélectionner les calques à afficher pour une tâche d’analyse particulière.

## Calques de profil de géographie {#section-4d9fb9b357764493a4d97d2b4068bb67}

Le [!DNL Geography] profil fournit un ensemble de calques d’images par défaut, qui sont stockés dans le dossier Profiles\Geography\Maps folder within the data workbench server installation directory :

* **Marbre bleu 2km :** Cette couche d&#39;image de terrain crée une carte 3D du monde, ce qui s&#39;affiche lorsque vous ajoutez la visualisation du globe à un espace de travail. Lorsque ce calque n’est pas sélectionné, le globe n’est pas visible, mais les autres calques s’affichent toujours. Le [!DNL Blue Marble 2km.layer] fichier fait référence au [!DNL Blue Marble 2km.tsi] fichier.

   Pour plus d’informations sur l’utilisation de la visualisation sur le globe, consultez le Guide *de l’utilisateur des outils de* données.

* **Points postaux :** Ce calque de point d’élément vous permet de mapper des emplacements dans votre jeu de données à l’aide d’un code postal des États-Unis. Le fichier [!DNL Zip Points.txt] de recherche (fourni par Adobe) contient une liste de tous les codes postaux des États-Unis et de la latitude et de la longitude de chaque code postal. Le [!DNL Zip Points.layer] fichier fait référence au [!DNL Zip Points.txt] fichier et au [!DNL Zipcode.dim] fichier et contient les paramètres de configuration nécessaires pour afficher les emplacements sur le globe. Chaque élément de la dimension Code postal ( [!DNL Zipcode.dim]) que vous définissez dans votre jeu de données est mappé sur le globe à l’aide de la latitude et de la longitude répertoriées pour ce code postal dans le fichier de [!DNL Zip Points.txt] recherche.

   Pour plus d’informations sur la définition des dimensions, voir le Guide de configuration des jeux de *données.*

* **Limites :** Cette couche vectorielle fournit les principales frontières politiques mondiales, comme les pays, ainsi que les limites des caractéristiques physiques naturelles de la Terre, comme les lacs et les îles. Le [!DNL Boundaries.layer] fichier fait référence à un ou plusieurs des [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec],  et  fichiers.[!DNL US states.vec][!DNL world boundaries.vec]

* **Coordonnées IP :** Ce calque de points d’élément utilise des points dynamiques pour vous permettre de mapper des emplacements dans votre jeu de données à l’aide d’adresses IP. Le [!DNL IP Coordinates.layer] fichier fait référence à la dimension Coordonnées ( [!DNL Coordinates.dim]) et indique la mesure Visiteurs comme mesure à utiliser pour déterminer la taille des points du globe pour chaque coordonnée.

Votre [!DNL Geography] profil ou d’autres profils dans votre installation peuvent contenir des couches d’images supplémentaires fournies par Adobe ou créées par votre entreprise.

## Création de nouveaux calques {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

Vous pouvez créer des calques d’images en copiant le type de fichier de calque approprié inclus dans le [!DNL Geography] profil dans n’importe quel dossier Profils\*nom du profil*\Mappages, puis en renommant et en modifiant le fichier selon les besoins. Tous les nouveaux calques doivent répondre aux exigences suivantes :

* Le [!DNL .layer] fichier doit respecter le format de l’un des types de calques pris en charge.
* Le [!DNL .layer] fichier doit faire référence aux fichiers de recherche et de dimension appropriés, si nécessaire.
* Le fichier de recherche référencé doit également être stocké dans le répertoire d’installation du serveur de l’outil de données et son chemin d’accès doit être spécifié avec précision dans le [!DNL .layer] fichier.

Pour plus d’informations sur le format et les paramètres de chaque type de fichier de calque et des fichiers associés, voir la section de ce chapitre pour le type de calque approprié.
