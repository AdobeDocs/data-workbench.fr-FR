---
description: Informations conceptuelles sur les calques de profil de la géographie, les types de calques d’imagerie et la création de nouveaux calques.
title: Comprendre les calques d’imagerie
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 1%

---

# Comprendre les calques d’imagerie{#understanding-imagery-layers}

Informations conceptuelles sur les calques de profil de la géographie, les types de calques d’imagerie et la création de nouveaux calques.

## Types de calques d&#39;image {#section-ce25364651a04cd1b83f9ac7c231fa41}

L’outil de données [!DNL Geography] vous permet de vue des types suivants de calques d’images dans l’outil de données :

* **Couche d&#39;image du sol :** ce type de couche affiche l&#39;imagerie du terrain de la Terre, sur laquelle les données géographiques peuvent être affichées. La visualisation du globe dans les outils de données est un exemple de couche d’image de terrain. Voir [Utilisation des calques d’image de terrain](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **Calque de point d’élément :** ce type de calque affiche un point sur le globe pour chaque élément d’une dimension. Voir [Utilisation des calques de points d’élément](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **Calque vectoriel :** ce type de calque affiche des données vectorielles (dessins au trait) sur le globe. Voir [Utilisation de calques vectoriels](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

Dans les outils de données, vous pouvez sélectionner les calques à afficher pour une tâche d’analyse particulière.

## Calques de Profil de géographie {#section-4d9fb9b357764493a4d97d2b4068bb67}

Le profil [!DNL Geography] fournit un ensemble de calques d’imagerie par défaut, qui sont stockés dans le dossier Profiles\Geography\Maps folder within the data workbench server installation directory :

* **Marbre bleu 2km :** Cette couche d&#39;image de relief crée une carte 3D du monde, qui s&#39;affiche lorsque vous ajoutez la visualisation du globe à un espace de travail. Lorsque ce calque n’est pas sélectionné, le globe n’est pas visible, mais les autres calques s’affichent toujours. Le fichier [!DNL Blue Marble 2km.layer] fait référence au fichier [!DNL Blue Marble 2km.tsi].

   Pour plus d’informations sur l’utilisation de la visualisation sur le globe, consultez le *Guide de l’utilisateur Data Workbench*.

* **Points postaux :** ce calque de points d’élément vous permet de mapper des emplacements dans votre jeu de données à l’aide d’un code postal des États-Unis. Le fichier de recherche [!DNL Zip Points.txt] (fourni par Adobe) contient une liste de tous les codes postaux des États-Unis ainsi que la latitude et la longitude de chaque code postal. Le fichier [!DNL Zip Points.layer] fait référence au fichier [!DNL Zip Points.txt] et au fichier [!DNL Zipcode.dim] et contient les paramètres de configuration nécessaires pour afficher les emplacements sur le globe. Chaque élément de la dimension Code postal ( [!DNL Zipcode.dim]) que vous définissez dans votre jeu de données est mappé sur le globe à l’aide de la latitude et de la longitude répertoriées pour ce code postal dans le fichier de recherche [!DNL Zip Points.txt].

   Pour plus d&#39;informations sur la définition des dimensions, consultez le *Guide de configuration des jeux de données.*

* **Limites :** Cette couche vectorielle fournit les principales frontières politiques mondiales, comme les pays, ainsi que les limites des caractéristiques physiques naturelles de la Terre, comme les lacs et les îles. Le fichier [!DNL Boundaries.layer] fait référence à un ou plusieurs des fichiers [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec] et [!DNL world boundaries.vec].

* **Coordonnées IP :** cette couche de points d’élément utilise des points dynamiques pour vous permettre de mapper des emplacements dans votre jeu de données à l’aide d’adresses IP. Le fichier [!DNL IP Coordinates.layer] fait référence à la dimension Coordonnées ( [!DNL Coordinates.dim]) et indique la mesure Visiteuse comme mesure à utiliser pour déterminer la taille des points du globe pour chaque coordonnée.

Votre profil [!DNL Geography] ou d&#39;autres profils de votre installation peuvent contenir d&#39;autres couches d&#39;images que l&#39;Adobe a fournies ou que votre société a créées.

## Création de nouveaux calques {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

Vous pouvez créer de nouveaux calques d’images en copiant le type de fichier de calques approprié inclus dans le profil [!DNL Geography] dans n’importe quel dossier de Profils\*nom du profil*\Maps, puis en renommant et en modifiant le fichier selon les besoins. Toutes les nouvelles couches doivent répondre aux exigences suivantes :

* Le fichier [!DNL .layer] doit respecter le format de l&#39;un des types de calques pris en charge.
* Le fichier [!DNL .layer] doit référencer les fichiers de recherche et de dimension appropriés, si nécessaire.
* Le fichier de recherche référencé doit également être stocké dans le répertoire d&#39;installation du serveur de l&#39;outil de données et son chemin d&#39;accès doit être spécifié avec précision dans le fichier [!DNL .layer].

Pour plus d&#39;informations sur le format et les paramètres de chaque type de fichier de calque et de ses fichiers associés, consultez la section de ce chapitre pour le type de calque approprié.
