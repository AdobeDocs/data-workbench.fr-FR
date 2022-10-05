---
description: Le fichier d’inclusion de jeu de données de traitement du journal pour un profil hérité contient des paramètres associés à la phase de traitement du journal de la construction du jeu de données.
title: Traitement de fichiers d’inclusion de jeux de données journaux
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
exl-id: 06d8046d-6bac-4ccd-bcef-06f7c9ec7619
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 3%

---

# Traitement de fichiers d’inclusion de jeux de données journaux{#log-processing-dataset-include-files}

{{eol}}

Le fichier d’inclusion de jeu de données de traitement du journal pour un profil hérité contient des paramètres associés à la phase de traitement du journal de la construction du jeu de données.

La première ligne d’un [!DNL Log Processing Dataset Include] Un fichier définit un type [!DNL LogProcessingInclude] qui prend en charge les paramètres Decoder Groups, Fields, Log Entry Condition, Parameters, Reprocess, Stage et Transformations. Tous les autres paramètres de traitement des journaux doivent être définis dans la variable [!DNL Log Processing.cfg] dans le répertoire du jeu de données du profil du jeu de données. Vous pouvez nommer une [!DNL Log Processing Dataset Include] fichier de tout ce que vous souhaitez, mais son extension doit être [!DNL .cfg]. Le fichier doit être stocké dans la variable *nom du profil hérité*\Dataset\Log Processing directory. Étant donné que les fichiers sont chargés de manière récursive pendant la phase de traitement des journaux de la construction du jeu de données, vous pouvez stocker la variable [!DNL Log Processing Dataset Include] fichiers à n’importe quel niveau du répertoire (par exemple, *nom du profil hérité*\Dataset\Log Processing\*nom du dossier*\*inclure le nom du fichier*.cfg).

>[!NOTE]
>
>De nombreux paramètres de configuration spécifiques au web pour Site sont définis dans [!DNL Log Processing Dataset Include] fichiers . Pour plus d’informations sur ces paramètres, voir [Paramètres de configuration des données web](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

<table id="table_E2112652CCD443E889A529EEDC4ADF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Groupes de décodeur </td> 
   <td colname="col2"> <p>Obligatoire si vous avez défini un fichier journal ou des sources de journaux de fichiers XML dans la variable <span class="filepath"> Log Processing.cfg</span> fichier . Le fichier texte ou les décodeurs XML que vous définissez pour extraire des champs de données du fichier journal et des sources de journaux XML. </p> <p> <b>Pour ajouter un nouveau groupe de décodeurs</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> Clic droit <span class="uicontrol"> Groupe de décodeur</span> et cliquez sur <span class="uicontrol"> Ajouter</span> &gt; <span class="uicontrol"> TextFileDecoderGroup</span> ou <span class="uicontrol"> XMLDecoderGroup</span>. </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> Dans le paramètre Name du nouveau groupe, saisissez le nom souhaité du groupe de décodeurs. </li> 
     </ul> </p> <p> <p>Remarque : Lorsque vous spécifiez un groupe de décodeur dans la variable <span class="filepath"> Log Processing.cfg</span> pour le profil du jeu de données, le nom doit correspondre exactement au nom que vous avez saisi ici. Pour plus d’informations, voir <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Fichiers journaux</a>. </p> </p> <p> Pour plus d’informations sur les décodeurs que vous pouvez définir pour chaque groupe, voir <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Groupes de décodeur de fichier texte</a> ou <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> Groupes de décodeur XML</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Champs </td> 
   <td colname="col2"> <p>Répertorie les champs définis dans <span class="wintitle"> Sources de journalisation</span> ou <span class="wintitle"> Transformations</span> dans <span class="wintitle"> Configuration du jeu de données de traitement du journal</span> mais utilisé dans des transformations, des conditions ou des dimensions étendues dans un <span class="wintitle"> Configuration des jeux de données de transformation</span> doit être répertorié ici. </p> <p> Chaque champ ci-dessous doit être répertorié dans certains <span class="wintitle"> Inclure le jeu de données de traitement du journal</span> fichier : 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition d’entrée du journal </td> 
   <td colname="col2"> <p>Facultatif. Définit les règles selon lesquelles les entrées de journal sont prises en compte pour inclusion dans le jeu de données. Voir <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condition d’entrée du journal</a>. </p> <p> <p>Remarque : Pour être inclus dans le jeu de données, une entrée de journal doit satisfaire à la variable <span class="wintitle"> Condition d’entrée du journal</span> dans le <span class="filepath"> Log Processing.cfg</span> et dans chaque <span class="wintitle"> Inclure le jeu de données de traitement du journal</span> fichier . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Paramètres </td> 
   <td colname="col2"> Facultatif. Variable que vous pouvez référencer dans d’autres paramètres de configuration. Pour plus d’informations, voir <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Définition des paramètres dans les fichiers d’inclusion de jeux de données</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Retraiter </td> 
   <td colname="col2"> <p>Facultatif. N’importe quel caractère ou combinaison de caractères peut être saisi ici. La modification de ce paramètre et l’enregistrement du fichier sur le serveur Data Workbench entraîne le retraitement des données. </p> <p> Pour plus d’informations sur le retraitement de vos données, voir <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Retraitement et retransformation</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Évaluation </td> 
   <td colname="col2"> <p>Facultatif. Nom de l’étape de traitement qui s’applique à cette étape <span class="wintitle"> Inclure le jeu de données de traitement du journal</span> fichier . Les étapes de traitement sont définies dans le paramètre Etapes du <span class="filepath"> Log Processing.cfg</span> fichier . </p> <p> <p>Remarque : Lorsque vous spécifiez une étape, le nom de l’étape doit correspondre exactement au nom répertorié dans le paramètre Etapes du <span class="filepath"> Log Processing.cfg</span> pour le profil du jeu de données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformations </td> 
   <td colname="col2"> Facultatif. Définit les transformations de données qui doivent être appliquées lors du traitement des journaux. Pour plus d’informations sur les types de transformation disponibles, voir <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformations de données</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Pour obtenir des descriptions des paramètres de la variable [!DNL Log Processing.cfg] fichier, voir [Fichier de configuration de traitement du journal](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

Gardez à l’esprit les points suivants lorsque vous utilisez des [!DNL Log Processing Dataset Include] files :

* La modification de l’un des paramètres de ce fichier nécessite le retraitement de toutes les données.
* Vous pouvez ajouter l’un des paramètres décrits ci-dessus au [!DNL Log Processing Dataset Include] en ouvrant et en modifiant le fichier dans le Bloc-notes. Toutes les modifications que vous apportez et enregistrez s’affichent lorsque vous rouvrez le fichier dans Data Workbench. Lors de l’ajout d’un nouveau paramètre, utilisez la touche Espace (et non la touche de tabulation) pour mettre en retrait deux (2) espaces à droite du niveau d’en-tête précédent.
