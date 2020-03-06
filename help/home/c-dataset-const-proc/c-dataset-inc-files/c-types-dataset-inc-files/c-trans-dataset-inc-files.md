---
description: Le fichier Transformation Dataset Include d’un profil hérité contient des paramètres associés à la phase de transformation de la construction du jeu de données.
solution: Analytics
title: Jeu de données de transformation - Inclure les fichiers
topic: Data workbench
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Jeu de données de transformation - Inclure les fichiers{#transformation-dataset-include-files}

Le fichier Transformation Dataset Include d’un profil hérité contient des paramètres associés à la phase de transformation de la construction du jeu de données.

La première ligne du fichier définit un type [!DNL TransformationInclude] qui prend en charge les paramètres Dimensions étendues, Paramètres, Retraitement, Phase et Transformations. Tous les autres paramètres doivent être définis dans le [!DNL Transformation.cfg] fichier du répertoire des jeux de données du profil de l’ensemble de données.

L’inclusion de paramètres autres que Dimensions étendues, Paramètres, Retraitement, Etape et Transformations dans un [!DNL Transformation Dataset Include] fichier génère des erreurs.

Vous pouvez nommer un [!DNL Transformation Dataset Include] fichier comme bon vous semble, mais son extension doit être [!DNL .cfg]. Le fichier doit être stocké dans le nom *de profil* hérité \Dataset\Transformation directory. Etant donné que les fichiers sont chargés de manière récursive pendant la phase de transformation de la construction du jeu de données, vous pouvez stocker les [!DNL Transformation Dataset Include] fichiers à n’importe quel niveau du répertoire (par exemple, nom *de profil* hérité \Dataset\Transformation\*nom du dossier*\*nom du fichier *.cfg).

>[!NOTE]
>
>De nombreux paramètres de configuration spécifiques au Web pour Site sont définis dans [!DNL Transformation Dataset Include] les fichiers. Pour plus d’informations sur ces paramètres, voir Paramètres [de configuration des données](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)Web.

Le tableau suivant décrit les paramètres disponibles dans un [!DNL Transformation Dataset Include] fichier :

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
   <td colname="col2"> Facultatif. Définit les dimensions étendues. Voir Dimensions <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"></a>étendues. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Paramètres </td> 
   <td colname="col2"> Facultatif. Variable que vous pouvez référencer dans d’autres paramètres de configuration. Pour plus d’informations, voir <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Définition de paramètres dans le jeu de données Inclure des fichiers</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Retraiter </td> 
   <td colname="col2"> <p>Facultatif. Tout caractère ou combinaison de caractères peut être saisi ici. La modification de ce paramètre et l’enregistrement du fichier initient la retransformation des données. </p> <p> Pour plus d’informations sur le retraitement de vos données, voir <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Retraitement et retransformation</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage </td> 
   <td colname="col2"> <p>Facultatif. Nom de l’étape de traitement qui s’applique à ce fichier d’inclusion <span class="wintitle"></span> du jeu de données de transformation. Les étapes de traitement sont définies dans le paramètre Etapes du fichier <span class="filepath"> Transformation.cfg</span> . </p> <p> <p>Remarque : Lorsque vous spécifiez une scène, le nom de la scène doit correspondre exactement au nom indiqué dans le paramètre Etapes du fichier <span class="filepath"> Transformation.cfg</span> pour le profil du jeu de données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformations </td> 
   <td colname="col2"> Facultatif. Définit les transformations de données à appliquer lors de la transformation. Pour plus d’informations sur les types de transformation disponibles, voir <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Data Transformations</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Pour obtenir la description des paramètres du [!DNL Transformation.cfg] fichier, voir Fichier [de configuration de](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md)transformation.

Gardez à l’esprit les points suivants lorsque vous travaillez avec [!DNL Transformation Dataset Include] des fichiers :

* La modification de l’un des paramètres de ce fichier nécessite une retransformation des données.
* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]et [!DNL AppendURI] les transformations ne fonctionnent que lorsqu’elles sont définies dans un [!DNL Transformation Dataset Configuration] fichier. Pour plus d’informations sur ces transformations, voir Transformations [de données](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* Vous pouvez ajouter n’importe lequel des paramètres décrits ci-dessus au [!DNL Transformation Dataset Include] fichier en ouvrant et en modifiant le fichier dans le Bloc-notes. Les modifications que vous apportez et enregistrez s’affichent lorsque vous rouvrez le fichier dans l’outil de données. Lors de l’ajout d’un nouveau paramètre, utilisez la touche Espace (et non la touche de tabulation) pour mettre en retrait deux (2) espaces à droite du niveau d’en-tête précédent.

Si vous vous abonnez au service de données [!DNL IP Geo-location] ou [!DNL IP Geo-intelligence] d’Adobe, Adobe vous fournit un profil interne composé d’un ensemble de transformations de données et de dimensions étendues créées spécifiquement pour le service de données. Les transformations et dimensions sont définies dans [!DNL Transformation Dataset Include] les fichiers inclus dans le répertoire Jeu de données du profil interne. Pour obtenir des instructions sur l’installation du profil interne pour le service [!DNL IP Geo-location] ou le service [!DNL IP Geo-intelligence] de données, consultez le Guide *de l’utilisateur des outils de* données.
