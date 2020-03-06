---
description: Le fichier Inclure le jeu de données de traitement de journal pour un profil hérité contient des paramètres associés à la phase de traitement de journal de la construction du jeu de données.
solution: Analytics
title: Jeu de données de traitement du journal Inclure les fichiers
topic: Data workbench
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Jeu de données de traitement du journal Inclure les fichiers{#log-processing-dataset-include-files}

Le fichier Inclure le jeu de données de traitement de journal pour un profil hérité contient des paramètres associés à la phase de traitement de journal de la construction du jeu de données.

La première ligne d’un [!DNL Log Processing Dataset Include] fichier définit un type [!DNL LogProcessingInclude] qui prend en charge les paramètres Groupes de décodeurs, Champs, Condition d’entrée dans le journal, Paramètres, Retraitement, Phase et Transformations. Tous les autres paramètres de traitement du journal doivent être définis dans le [!DNL Log Processing.cfg] fichier du répertoire des jeux de données du profil du jeu de données. Vous pouvez nommer un [!DNL Log Processing Dataset Include] fichier comme bon vous semble, mais son extension doit être [!DNL .cfg]. Le fichier doit être stocké dans le nom *de profil* hérité \Dataset\Log Processing directory. Etant donné que les fichiers sont chargés de manière récursive pendant la phase de traitement du journal de la construction des jeux de données, vous pouvez stocker les [!DNL Log Processing Dataset Include] fichiers à n’importe quel niveau du répertoire (par exemple, nom ** de profil\Dataset\Log Processing\*nom du dossier*\*nom du fichier*.cfg).

>[!NOTE]
>
>De nombreux paramètres de configuration spécifiques au Web pour Site sont définis dans [!DNL Log Processing Dataset Include] les fichiers. Pour plus d’informations sur ces paramètres, voir Paramètres [de configuration des données](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)Web.

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
   <td colname="col2"> <p>Obligatoire si vous avez défini des sources de fichiers journaux ou des fichiers XML dans le fichier <span class="filepath"> Log Processing.cfg</span> . Fichier texte ou décodeurs XML que vous définissez pour extraire des champs de données du fichier journal et des sources de journaux XML. </p> <p> <b>Pour ajouter un nouveau groupe de décodeurs</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> Cliquez avec le bouton droit de la souris sur Groupe <span class="uicontrol"></span> décodeur et cliquez sur <span class="uicontrol"> Ajouter nouveau</span> &gt; <span class="uicontrol"> TextFileDecoderGroup</span> ou <span class="uicontrol"> XMLDecoderGroup.</span> </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> Dans le paramètre Name du nouveau groupe, saisissez le nom souhaité du groupe de décodeurs. </li> 
     </ul> </p> <p> <p>Remarque :  Lorsque vous spécifiez un groupe de décodeurs dans le fichier <span class="filepath"> Log Processing.cfg</span> pour le profil du jeu de données, le nom doit correspondre exactement au nom saisi ici. Pour plus d’informations, voir Fichiers <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"></a>journaux. </p> </p> <p> Pour plus d’informations sur les décodeurs que vous pouvez définir pour chaque groupe, voir Groupes <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> de décodeurs de fichiers</a> texte ou Groupes <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> de décodeurs</a>XML. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Champs </td> 
   <td colname="col2"> <p>Répertorie les champs définis dans les sources <span class="wintitle"> de journal ou les transformations</span> dans un fichier de configuration <span class="wintitle"> de jeux de données de</span> <span class="wintitle"></span> <span class="wintitle"> traitement de journal, mais utilisés dans des transformations, des conditions ou des dimensions étendues dans un fichier de configuration de jeux de données de transformation.</span> </p> <p> Chaque champ ci-dessous doit être répertorié dans un fichier d’inclusion <span class="wintitle"> du jeu de données de traitement du</span> journal : 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition d’entrée de journal </td> 
   <td colname="col2"> <p>Facultatif. Définit les règles selon lesquelles les entrées du journal sont prises en compte pour l’inclusion dans le jeu de données. Voir Condition <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"></a>d’entrée de journal. </p> <p> <p>Remarque :  Pour être incluse dans le jeu de données, une entrée de journal doit satisfaire à la condition <span class="wintitle"> d'entrée de journal dans le fichier</span> Log Processing.cfg <span class="filepath"> et dans chaque fichier</span> Log Processing Data Set Include <span class="wintitle"></span> . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Paramètres </td> 
   <td colname="col2"> Facultatif. Variable que vous pouvez référencer dans d’autres paramètres de configuration. Pour plus d’informations, voir <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Définition de paramètres dans le jeu de données Inclure des fichiers</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Retraiter </td> 
   <td colname="col2"> <p>Facultatif. Tout caractère ou combinaison de caractères peut être saisi ici. La modification de ce paramètre et l’enregistrement du fichier sur le serveur de l’outil de données initie le retraitement des données. </p> <p> Pour plus d’informations sur le retraitement de vos données, voir <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Retraitement et retransformation</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage </td> 
   <td colname="col2"> <p>Facultatif. Nom de l’étape de traitement qui s’applique à ce fichier d’inclusion <span class="wintitle"> du jeu de données de traitement du</span> journal. Les étapes de traitement sont définies dans le paramètre Etapes du fichier <span class="filepath"> Log Processing.cfg</span> . </p> <p> <p>Remarque :  Lorsque vous spécifiez une scène, le nom de la scène doit correspondre exactement au nom indiqué dans le paramètre Etapes du fichier <span class="filepath"> Log Processing.cfg</span> pour le profil du jeu de données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformations </td> 
   <td colname="col2"> Facultatif. Définit les transformations de données à appliquer lors du traitement des journaux. Pour plus d’informations sur les types de transformation disponibles, voir <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Data Transformations</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Pour obtenir la description des paramètres du [!DNL Log Processing.cfg] fichier, voir Fichier [de configuration de traitement des](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)journaux.

Gardez à l’esprit les points suivants lorsque vous travaillez avec [!DNL Log Processing Dataset Include] des fichiers :

* La modification de l’un des paramètres de ce fichier nécessite le retraitement de toutes les données.
* Vous pouvez ajouter n’importe lequel des paramètres décrits ci-dessus au [!DNL Log Processing Dataset Include] fichier en ouvrant et en modifiant le fichier dans le Bloc-notes. Les modifications que vous apportez et enregistrez s’affichent lorsque vous rouvrez le fichier dans l’outil de données. Lors de l’ajout d’un nouveau paramètre, utilisez la touche Espace (et non la touche de tabulation) pour mettre en retrait deux (2) espaces à droite du niveau d’en-tête précédent.

