---
description: Informations conceptuelles sur les calques de profil Geography, les types de calques d’imagerie et la création de calques.
title: Comprendre les calques d’imagerie
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# Comprendre les calques d’imagerie{#understanding-imagery-layers}

Informations conceptuelles sur les calques de profil Geography, les types de calques d’imagerie et la création de calques.

## Types de calques d’imagerie {#section-ce25364651a04cd1b83f9ac7c231fa41}

Data Workbench [!DNL Geography] vous permet d’afficher les types de calques d’imagerie suivants dans Data Workbench :

* **Couche d’image du terrain :** ce type de couche affiche l’imagerie du terrain de la Terre, sur laquelle des données géographiques peuvent être affichées. La visualisation en globe dans Data Workbench est un exemple de couche d’image du terrain. Voir [Utilisation des calques d’image du terrain](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **Calque de point d’élément :**  ce type de calque affiche un point sur le globe pour chaque élément d’une dimension. Voir [Utilisation des calques de point d’élément](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **Couche vectorielle :** ce type de couche affiche des données vectorielles (dessins au trait) sur le globe. Voir [Utilisation des calques vectoriels](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

Dans Data Workbench, vous pouvez sélectionner les calques à afficher pour une tâche d’analyse particulière.

## Calques de profil de géographie {#section-4d9fb9b357764493a4d97d2b4068bb67}

Le profil [!DNL Geography] vous fournit un ensemble de calques d’imagerie par défaut, stockés dans le dossier Profiles\Geography\Maps folder within the data workbench server installation directory :

* **Marbre bleu 2km :** cette couche d’image du terrain crée une carte en 3D du monde, qui s’affiche lorsque vous ajoutez la visualisation du globe à un espace de travail. Lorsque ce calque n’est pas sélectionné, le globe n’est pas visible, mais les autres calques s’affichent toujours. Le fichier [!DNL Blue Marble 2km.layer] référence le fichier [!DNL Blue Marble 2km.tsi].

   Pour plus d’informations sur l’utilisation de la visualisation du globe, consultez le *Guide de l’utilisateur du Data Workbench*.

* **Zip Points :** cette couche de point d’élément vous permet de mapper des emplacements dans votre jeu de données à l’aide d’un code postal des États-Unis. Le fichier de recherche [!DNL Zip Points.txt] (fourni par Adobe) contient une liste de tous les codes postaux des États-Unis, ainsi que la latitude et la longitude de chaque code postal. Le fichier [!DNL Zip Points.layer] référence le fichier [!DNL Zip Points.txt] et le fichier [!DNL Zipcode.dim] et contient les paramètres de configuration nécessaires pour afficher les emplacements sur le globe. Chaque élément de la dimension Code postal ( [!DNL Zipcode.dim]) que vous définissez dans votre jeu de données est mappé sur le globe à l’aide de la latitude et de la longitude répertoriées pour ce code postal dans le fichier de recherche [!DNL Zip Points.txt].

   Pour plus d’informations sur la définition de dimensions, consultez le *Guide de configuration des jeux de données.*

* **Limites :** cette couche vectorielle fournit les principales frontières politiques mondiales, comme les pays, ainsi que les limites des caractéristiques physiques naturelles de la Terre, comme les lacs et les îles. Le fichier [!DNL Boundaries.layer] fait référence à un ou plusieurs des fichiers [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec] et [!DNL world boundaries.vec].

* **Coordonnées IP :** cette couche de point d’élément utilise des points dynamiques pour vous permettre de mapper des emplacements dans votre jeu de données à l’aide d’adresses IP. Le fichier [!DNL IP Coordinates.layer] fait référence à la dimension Coordonnées ( [!DNL Coordinates.dim]) et spécifie la mesure Visiteurs comme mesure à utiliser pour déterminer la taille des points sur la globe pour chaque coordonnée.

Votre profil [!DNL Geography] ou d’autres profils de votre installation peuvent contenir des calques d’imagerie supplémentaires qui s’Adobe fournis pour votre entreprise créée.

## Création de calques {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

Vous pouvez créer de nouveaux calques d’imagerie en copiant le type de fichier de calque approprié inclus dans le profil [!DNL Geography] dans n’importe quel dossier Profils\*nom du profil*\Mappages , puis en renommant et en modifiant le fichier selon les besoins. Toutes les nouvelles couches doivent répondre aux exigences suivantes :

* Le fichier [!DNL .layer] doit respecter le format de l’un des types de calques pris en charge.
* Si nécessaire, le fichier [!DNL .layer] doit faire référence aux fichiers de recherche et de dimension appropriés.
* Le fichier de recherche référencé doit également être stocké dans le répertoire d’installation du serveur Data Workbench et son chemin d’accès doit être spécifié avec précision dans le fichier [!DNL .layer].

Pour plus d’informations sur le format et les paramètres de chaque type de fichier de calque et des fichiers associés, consultez la section de ce chapitre pour le type de calque approprié.
