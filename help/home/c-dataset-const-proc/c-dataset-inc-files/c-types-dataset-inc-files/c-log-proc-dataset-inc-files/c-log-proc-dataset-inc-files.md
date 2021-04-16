---
description: Le fichier Inclure le jeu de données de traitement du journal pour un profil hérité contient des paramètres associés à la phase de traitement du journal de la construction du jeu de données.
title: Traitement de fichiers d’inclusion de jeux de données journaux
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
exl-id: 06d8046d-6bac-4ccd-bcef-06f7c9ec7619
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 3%

---

# Traitement de fichiers d’inclusion de jeux de données journaux{#log-processing-dataset-include-files}

Le fichier Inclure le jeu de données de traitement du journal pour un profil hérité contient des paramètres associés à la phase de traitement du journal de la construction du jeu de données.

La première ligne d&#39;un fichier [!DNL Log Processing Dataset Include] définit un type [!DNL LogProcessingInclude] qui prend en charge les paramètres Decoder Groups, Fields, Log Entry Condition, Parameters, Reprocess, Stage et Transformations. Tous les autres paramètres de traitement du journal doivent être définis dans le fichier [!DNL Log Processing.cfg] du répertoire des jeux de données du profil de données. Vous pouvez nommer un fichier [!DNL Log Processing Dataset Include] comme bon vous semble, mais son extension doit être [!DNL .cfg]. Le fichier doit être stocké dans le *nom de profil hérité*\Dataset\Log Processing directory. Etant donné que les fichiers sont chargés de manière récursive pendant la phase de traitement du journal de la construction du jeu de données, vous pouvez stocker les fichiers [!DNL Log Processing Dataset Include] à n’importe quel niveau du répertoire (par exemple, *nom du profil hérité*\Dataset\Log Processing\*nom du dossier*\*nom du fichier*.cfg).

>[!NOTE]
>
>De nombreux paramètres de configuration spécifiques au Web pour Site sont définis dans les fichiers [!DNL Log Processing Dataset Include]. Pour plus d&#39;informations sur ces paramètres, voir [Paramètres de configuration pour les données Web](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

<table id="table_E2112652CCD443E889A529EEDC4ADF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Groupes de décodeurs </td> 
   <td colname="col2"> <p>Obligatoire si vous avez défini des sources de journaux de fichiers journaux ou XML dans le fichier <span class="filepath"> Log Processing.cfg</span>. Fichier texte ou décodeurs XML que vous définissez pour extraire des champs de données du fichier journal et des sources de journaux XML. </p> <p> <b>Pour ajouter un nouveau groupe de décodeurs</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> Cliquez avec le bouton droit de la souris sur <span class="uicontrol"> Decoder Group</span> et cliquez sur <span class="uicontrol"> Ajouter nouveau</span> &gt; <span class="uicontrol"> TextFileDecoderGroup</span> ou <span class="uicontrol"> XMLDecoderGroup</span>. </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> Dans le paramètre Name du nouveau groupe, saisissez le nom souhaité du groupe de décodeurs. </li> 
     </ul> </p> <p> <p>Remarque :  Lorsque vous spécifiez un groupe de décodeurs dans le fichier <span class="filepath"> Log Processing.cfg</span> pour le profil de jeux de données, le nom doit correspondre exactement au nom que vous saisissez ici. Pour plus d’informations, voir <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Fichiers journaux</a>. </p> </p> <p> Pour plus d’informations sur les décodeurs que vous pouvez définir pour chaque groupe, voir <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Groupes de décodeurs de fichiers texte</a> ou <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> Groupes de décodeurs XML</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Champs </td> 
   <td colname="col2"> <p>Les champs de listes définis dans <span class="wintitle"> Sources de données de traitement du journal</span> ou <span class="wintitle"> Transformations</span> dans un fichier <span class="wintitle"> Configuration du jeu de données de traitement du journal</span>, mais utilisés dans des transformations, des conditions ou des dimensions étendues dans un fichier <span class="wintitle"> Configuration du jeu de données de transformation</span> doivent être répertoriés ici. </p> <p> Chaque champ ci-dessous doit être répertorié dans un fichier <span class="wintitle"> Jeu de données de traitement du journal Inclure</span> : 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition d’entrée du journal </td> 
   <td colname="col2"> <p>Facultatif. Définit les règles selon lesquelles les entrées du journal sont prises en compte pour l’inclusion dans le jeu de données. Voir <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condition d’entrée de journal</a>. </p> <p> <p>Remarque :  Pour être inclus dans le jeu de données, une entrée de journal doit satisfaire à la <span class="wintitle"> condition d'entrée de journal</span> dans le fichier <span class="filepath"> Log Processing.cfg</span> et dans chaque fichier <span class="wintitle"> Log Processing Dataset Include</span>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Paramètres </td> 
   <td colname="col2"> Facultatif. Variable que vous pouvez référencer dans d’autres paramètres de configuration. Pour plus d'informations, voir <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Définir des paramètres dans le jeu de données Inclure des fichiers</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Retraiter </td> 
   <td colname="col2"> <p>Facultatif. Tout caractère ou combinaison de caractères peut être saisi ici. La modification de ce paramètre et l’enregistrement du fichier sur le serveur de l’outil de données initie le retraitement des données. </p> <p> Pour plus d’informations sur le retraitement de vos données, voir <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Retraitement et retransformation</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Étape </td> 
   <td colname="col2"> <p>Facultatif. Nom de l’étape de traitement qui s’applique à ce fichier <span class="wintitle"> Jeu de données de traitement du journal Inclure </span>. Les étapes de traitement sont définies dans le paramètre Etapes du fichier <span class="filepath"> Log Processing.cfg</span>. </p> <p> <p>Remarque :  Lorsque vous spécifiez une étape, le nom de la phase doit correspondre exactement au nom indiqué dans le paramètre Etapes du fichier <span class="filepath"> Log Processing.cfg</span> pour le profil du jeu de données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformations </td> 
   <td colname="col2"> Facultatif. Définit les transformations de données à appliquer lors du traitement des journaux. Pour plus d'informations sur les types de transformation disponibles, voir <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Data Transformations</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Pour obtenir la description des paramètres du fichier [!DNL Log Processing.cfg], voir [Fichier de configuration de traitement du journal](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

Tenez compte des points suivants lorsque vous travaillez avec des fichiers [!DNL Log Processing Dataset Include] :

* La modification des paramètres de ce fichier nécessite le retraitement de toutes les données.
* Vous pouvez ajouter n&#39;importe lequel des paramètres décrits ci-dessus au fichier [!DNL Log Processing Dataset Include] en ouvrant et en modifiant le fichier dans le Bloc-notes. Les modifications que vous apportez et enregistrez s’affichent lorsque vous rouvrez le fichier dans l’outil de données. Lors de l’ajout d’un nouveau paramètre, utilisez la touche Espace (et non la touche de tabulation) pour mettre en retrait deux (2) espaces à droite du niveau d’en-tête précédent.
