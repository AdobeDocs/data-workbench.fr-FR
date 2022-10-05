---
description: Informations conceptuelles sur les calques de profil Geography, les types de calques d’imagerie et la création de calques.
title: Comprendre les calques d’imagerie
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# Comprendre les calques d’imagerie{#understanding-imagery-layers}

{{eol}}

Informations conceptuelles sur les calques de profil Geography, les types de calques d’imagerie et la création de calques.

## Types de calques d’imagerie {#section-ce25364651a04cd1b83f9ac7c231fa41}

Data Workbench [!DNL Geography] vous permet d’afficher les types de calques d’imagerie suivants dans Data Workbench :

* **Couche d’image du terrain :** Ce type de couche affiche les images du terrain de la Terre, sur lesquelles les données géographiques peuvent être affichées. La visualisation en globe dans Data Workbench est un exemple de couche d’image du terrain. Voir [Utilisation des calques d’image du terrain](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **Couche de point d’élément :** Ce type de calque affiche un point sur le globe pour chaque élément d’une dimension. Voir [Utilisation des calques de point d’élément](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **Couche vectorielle :** Ce type de calque affiche des données vectorielles (dessins au trait) sur le globe. Voir [Utilisation des calques vectoriels](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

Dans Data Workbench, vous pouvez sélectionner les calques à afficher pour une tâche d’analyse particulière.

## Calques de profil de géographie {#section-4d9fb9b357764493a4d97d2b4068bb67}

Le [!DNL Geography] profile vous fournit un ensemble de calques d’imagerie par défaut, qui sont stockés dans le dossier Profils\Geography\Maps du répertoire d’installation du serveur Data Workbench :

* **Marbre bleu 2km :** Cette couche d’image du terrain crée une carte 3D du monde, qui s’affiche lorsque vous ajoutez la visualisation du globe à un espace de travail. Lorsque ce calque n’est pas sélectionné, le globe n’est pas visible, mais les autres calques s’affichent toujours. Le [!DNL Blue Marble 2km.layer] référence le fichier [!DNL Blue Marble 2km.tsi] fichier .

   Pour plus d’informations sur l’utilisation de la visualisation du globe, voir *Guide de l’utilisateur de Data Workbench*.

* **Zip Points :** Cette couche de point d’élément vous permet de mapper des emplacements dans votre jeu de données à l’aide d’un code postal des États-Unis. Le [!DNL Zip Points.txt] Le fichier de recherche (fourni par Adobe) contient une liste de tous les codes postaux des États-Unis ainsi que la latitude et la longitude de chaque code postal. Le [!DNL Zip Points.layer] référence le fichier [!DNL Zip Points.txt] et le fichier [!DNL Zipcode.dim] et contient les paramètres de configuration nécessaires pour afficher les emplacements sur le globe. Chaque élément de la dimension Code postal ( [!DNL Zipcode.dim]) que vous définissez dans votre jeu de données est mappé sur le globe à l’aide de la latitude et de la longitude répertoriées pour ce code postal dans la variable [!DNL Zip Points.txt] fichier de recherche.

   Pour plus d’informations sur la définition des dimensions, voir *Guide de configuration des jeux de données.*

* **Limites :** Cette couche vectorielle fournit les principales frontières politiques mondiales, comme les pays, ainsi que les limites des caractéristiques physiques naturelles de la Terre, comme les lacs et les îles. Le [!DNL Boundaries.layer] référence un ou plusieurs des [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec], et [!DNL world boundaries.vec] fichiers .

* **Coordonnées IP :** Cette couche de point d’élément utilise des points dynamiques pour vous permettre de mapper des emplacements dans votre jeu de données à l’aide d’adresses IP. Le [!DNL IP Coordinates.layer] référence la dimension Coordonnées ( [!DNL Coordinates.dim]) et spécifie la mesure Visiteurs comme mesure à utiliser pour déterminer la taille des points sur la globe pour chaque coordonnée.

Votre [!DNL Geography] Le profil ou d’autres profils de votre installation peuvent contenir des calques d’imagerie supplémentaires qui Adobes les données fournies ou votre société créée.

## Création de calques {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

Vous pouvez créer de nouveaux calques d’imagerie en copiant le type de fichier de calque approprié inclus dans la variable [!DNL Geography] dans n’importe quel dossier Profils\*nom du profil*\Mappe, puis renommez et modifiez le fichier selon les besoins. Toutes les nouvelles couches doivent répondre aux exigences suivantes :

* Le [!DNL .layer] doit respecter le format de l’un des types de calques pris en charge.
* Le [!DNL .layer] le cas échéant, vous devez référencer les fichiers de recherche et de dimension appropriés.
* Le fichier de recherche référencé doit également être stocké dans le répertoire d’installation du serveur Data Workbench et son chemin d’accès doit être spécifié avec précision dans la variable [!DNL .layer] fichier .

Pour plus d’informations sur le format et les paramètres de chaque type de fichier de calque et des fichiers associés, consultez la section de ce chapitre pour le type de calque approprié.
