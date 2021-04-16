---
description: Le fichier Transformation Dataset Include pour un profil hérité contient des paramètres associés à la phase de transformation de la construction du jeu de données.
title: Fichiers d’inclusion de jeux de données de transformation
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
exl-id: 58793f82-162a-4d43-aea9-163716c82db6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 3%

---

# Fichiers d’inclusion de jeux de données de transformation{#transformation-dataset-include-files}

Le fichier Transformation Dataset Include pour un profil hérité contient des paramètres associés à la phase de transformation de la construction du jeu de données.

La première ligne du fichier définit un type [!DNL TransformationInclude] qui prend en charge les paramètres de Dimensions étendues, de paramètres, de retraitement, d&#39;étape et de transformations. Tous les autres paramètres doivent être définis dans le fichier [!DNL Transformation.cfg] du répertoire de jeux de données du profil de données.

L’inclusion de paramètres autres que les Dimensions étendues, les paramètres, le retraitement, l’étape et les transformations dans un fichier [!DNL Transformation Dataset Include] génère des erreurs.

Vous pouvez nommer un fichier [!DNL Transformation Dataset Include] comme bon vous semble, mais son extension doit être [!DNL .cfg]. Le fichier doit être stocké dans le *nom de profil hérité*\Dataset\Transformation directory. Etant donné que les fichiers sont chargés de manière récursive pendant la phase de transformation de la construction du jeu de données, vous pouvez stocker les fichiers [!DNL Transformation Dataset Include] à n’importe quel niveau du répertoire (par exemple, *nom de profil hérité*\Dataset\Transformation\*nom du dossier*\*nom du fichier*.cfg).

>[!NOTE]
>
>De nombreux paramètres de configuration spécifiques au Web pour Site sont définis dans les fichiers [!DNL Transformation Dataset Include]. Pour plus d&#39;informations sur ces paramètres, voir [Paramètres de configuration pour les données Web](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

Le tableau suivant décrit les paramètres disponibles dans un fichier [!DNL Transformation Dataset Include] :

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
   <td colname="col2"> Facultatif. Variable que vous pouvez référencer dans d’autres paramètres de configuration. Pour plus d'informations, voir <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Définir des paramètres dans le jeu de données Inclure des fichiers</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Retraiter </td> 
   <td colname="col2"> <p>Facultatif. Tout caractère ou combinaison de caractères peut être saisi ici. La modification de ce paramètre et l'enregistrement du fichier initient la retransformation des données. </p> <p> Pour plus d’informations sur le retraitement de vos données, voir <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Retraitement et retransformation</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Étape </td> 
   <td colname="col2"> <p>Facultatif. Nom de l'étape de traitement qui s'applique à ce fichier <span class="wintitle"> Jeu de données de transformation Inclure </span>. Les étapes de traitement sont définies dans le paramètre Etapes du fichier <span class="filepath"> Transformation.cfg</span>. </p> <p> <p>Remarque : Lorsque vous spécifiez une scène, le nom de la scène doit correspondre exactement au nom indiqué dans le paramètre Etapes du fichier <span class="filepath"> Transformation.cfg</span> pour le profil de jeux de données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformations </td> 
   <td colname="col2"> Facultatif. Définit les transformations de données à appliquer lors de la transformation. Pour plus d'informations sur les types de transformation disponibles, voir <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Data Transformations</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Pour obtenir la description des paramètres du fichier [!DNL Transformation.cfg], voir [Transformation Configuration File](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

Tenez compte des points suivants lorsque vous travaillez avec des fichiers [!DNL Transformation Dataset Include] :

* La modification des paramètres de ce fichier nécessite une retransformation des données.
* [!DNL CrossRows],  [!DNL ODBCLookup],  [!DNL Sessionize] et  [!DNL AppendURI] les transformations ne fonctionnent que lorsqu’elles sont définies dans un  [!DNL Transformation Dataset Configuration] fichier. Pour plus d’informations sur ces transformations, voir [Transformations de données](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* Vous pouvez ajouter n&#39;importe lequel des paramètres décrits ci-dessus au fichier [!DNL Transformation Dataset Include] en ouvrant et en modifiant le fichier dans le Bloc-notes. Les modifications que vous apportez et enregistrez s’affichent lorsque vous rouvrez le fichier dans l’outil de données. Lors de l’ajout d’un nouveau paramètre, utilisez la touche Espace (et non la touche de tabulation) pour mettre en retrait deux (2) espaces à droite du niveau d’en-tête précédent.

Si vous vous abonnez au service de données de l&#39;Adobe [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence], l&#39;Adobe vous fournit un profil interne composé d&#39;un ensemble de transformations de données et de dimensions étendues créées spécifiquement pour le service de données. Les transformations et dimensions sont définies dans des fichiers [!DNL Transformation Dataset Include] inclus dans le répertoire Dataset du profil interne. Pour obtenir des instructions sur l&#39;installation du profil interne pour le service de données [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence], consultez le *Guide de l&#39;utilisateur Data Workbench*.
