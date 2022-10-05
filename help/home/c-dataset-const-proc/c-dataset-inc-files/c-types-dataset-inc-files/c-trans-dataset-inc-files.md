---
description: Le fichier d’inclusion de jeu de données de transformation pour un profil hérité contient des paramètres associés à la phase de transformation de la construction du jeu de données.
title: Fichiers d’inclusion de jeux de données de transformation
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
exl-id: 58793f82-162a-4d43-aea9-163716c82db6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 3%

---

# Fichiers d’inclusion de jeux de données de transformation{#transformation-dataset-include-files}

{{eol}}

Le fichier d’inclusion de jeu de données de transformation pour un profil hérité contient des paramètres associés à la phase de transformation de la construction du jeu de données.

La première ligne du fichier définit un type [!DNL TransformationInclude] qui prend en charge les paramètres de Dimensions étendues, de paramètres, de retraitement, d’évaluation et de transformations. Tous les autres paramètres doivent être définis dans la variable [!DNL Transformation.cfg] dans le répertoire du jeu de données du profil du jeu de données.

Inclusion de paramètres autres que les Dimensions étendues, les paramètres, le retraitement, l’évaluation et les transformations dans une [!DNL Transformation Dataset Include] génère des erreurs.

Vous pouvez nommer une [!DNL Transformation Dataset Include] fichier de tout ce que vous souhaitez, mais son extension doit être [!DNL .cfg]. Le fichier doit être stocké dans la variable *nom du profil hérité*\Dataset\Transformation directory. Comme les fichiers sont chargés de manière récursive pendant la phase de transformation de la construction du jeu de données, vous pouvez stocker la variable [!DNL Transformation Dataset Include] fichiers à n’importe quel niveau du répertoire (par exemple, *nom du profil hérité*\Dataset\Transformation\*nom du dossier*\*nom du fichier d’inclusion*.cfg).

>[!NOTE]
>
>De nombreux paramètres de configuration spécifiques au web pour Site sont définis dans [!DNL Transformation Dataset Include] fichiers . Pour plus d’informations sur ces paramètres, voir [Paramètres de configuration des données web](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

Le tableau suivant décrit les paramètres disponibles dans une [!DNL Transformation Dataset Include] fichier :

<table id="table_7BD343888D9145BCBA889B531A4D18F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimensions étendues </td> 
   <td colname="col2"> Facultatif. Définit les dimensions étendues. Voir <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Dimensions étendues</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Paramètres </td> 
   <td colname="col2"> Facultatif. Variable que vous pouvez référencer dans d’autres paramètres de configuration. Pour plus d’informations, voir <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Définition des paramètres dans les fichiers d’inclusion de jeux de données</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Retraiter </td> 
   <td colname="col2"> <p>Facultatif. N’importe quel caractère ou combinaison de caractères peut être saisi ici. La modification de ce paramètre et l’enregistrement du fichier initie la retransformation des données. </p> <p> Pour plus d’informations sur le retraitement de vos données, voir <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Retraitement et retransformation</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Évaluation </td> 
   <td colname="col2"> <p>Facultatif. Nom de l’étape de traitement qui s’applique à cette étape <span class="wintitle"> Inclure le jeu de données de transformation</span> fichier . Les étapes de traitement sont définies dans le paramètre Etapes du <span class="filepath"> Transformation.cfg</span> fichier . </p> <p> <p>Remarque : Lorsque vous spécifiez une étape, le nom de l’étape doit correspondre exactement au nom répertorié dans le paramètre Etapes du <span class="filepath"> Transformation.cfg</span> pour le profil du jeu de données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformations </td> 
   <td colname="col2"> Facultatif. Définit les transformations de données à appliquer lors de la transformation. Pour plus d’informations sur les types de transformation disponibles, voir <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformations de données</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Pour obtenir des descriptions des paramètres de la variable [!DNL Transformation.cfg] fichier, voir [Fichier de configuration de transformation](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

Gardez à l’esprit les points suivants lorsque vous utilisez des [!DNL Transformation Dataset Include] files :

* La modification des paramètres de ce fichier nécessite une retransformation des données.
* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize], et [!DNL AppendURI] les transformations ne fonctionnent que lorsqu’elles sont définies dans une [!DNL Transformation Dataset Configuration] fichier . Pour plus d’informations sur ces transformations, voir [Transformations de données](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* Vous pouvez ajouter l’un des paramètres décrits ci-dessus au [!DNL Transformation Dataset Include] en ouvrant et en modifiant le fichier dans le Bloc-notes. Toutes les modifications que vous apportez et enregistrez s’affichent lorsque vous rouvrez le fichier dans Data Workbench. Lors de l’ajout d’un nouveau paramètre, utilisez la touche Espace (et non la touche de tabulation) pour mettre en retrait deux (2) espaces à droite du niveau d’en-tête précédent.

Si vous vous abonnez à Adobe [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] service de données, Adobe vous fournit un profil interne constitué d’un ensemble de transformations de données et de dimensions étendues créées spécifiquement pour le service de données. Les transformations et dimensions sont définies dans la section [!DNL Transformation Dataset Include] fichiers inclus dans le répertoire du jeu de données du profil interne. Pour obtenir des instructions sur l’installation du profil interne pour la variable [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] service de données, voir *Guide de l’utilisateur de Data Workbench*.
