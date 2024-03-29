---
description: Étapes de modification du fichier Transformation.cfg pour un profil de jeu de données.
title: Modification du fichier de configuration de transformation
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
exl-id: 3fab17a4-d356-4548-b977-f5d409870753
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 2%

---

# Modification du fichier de configuration de transformation{#editing-the-transformation-configuration-file}

{{eol}}

Étapes de modification du fichier Transformation.cfg pour un profil de jeu de données.

1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez la variable [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour afficher son contenu.

   Pour plus d’informations sur l’ouverture et l’utilisation de la variable [!DNL Profile Manager], reportez-vous à la section *Guide de l’utilisateur de Data Workbench*.

   >[!NOTE]
   >
   >Un sous-répertoire de transformation peut exister dans le répertoire du jeu de données. Ce sous-répertoire contient la variable [!DNL Transformation Dataset Include] fichiers créés pour un ou plusieurs profils hérités. Pour plus d’informations sur [!DNL Transformation Dataset Include] fichiers, voir [Fichiers d’inclusion de jeux de données](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL Transformation.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la variable [!DNL User] colonne .
1. Cliquez avec le bouton droit de la souris sur la coche que vous venez de créer, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. Le [!DNL Transformation.cfg] s’affiche.

   Vous pouvez également ouvrir le [!DNL Transformation.cfg] à partir d’un fichier [!DNL Transformation Dependency Map]. Pour plus d’informations sur [!DNL transformation dependency maps], voir [Outils de configuration des jeux de données](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. Editez les paramètres du fichier de configuration à partir du tableau suivant comme guide.

   Lors de la modification de la variable [!DNL Transformation.cfg] dans une fenêtre Data Workbench, vous pouvez utiliser des raccourcis clavier pour les fonctions d’édition de base, notamment couper (Ctrl+x ), copier (Ctrl+c), coller (Ctrl+v ), annuler (Ctrl+z ), rétablir (Ctrl+Maj+z ), sélectionner une section (cliquer+faire glisser), tout sélectionner (Ctrl+a ). En outre, vous pouvez utiliser les raccourcis pour copier et coller du texte d’un fichier de configuration ( [!DNL .cfg]) à un autre.

   >[!NOTE]
   >
   >A [!DNL Transformation Dataset Include] Les fichiers d’un profil hérité contiennent un sous-ensemble des paramètres décrits dans le tableau suivant, ainsi que certains paramètres supplémentaires. Pour plus d’informations sur [!DNL Transformation Dataset Include] fichiers, voir [Fichiers d’inclusion de jeux de données](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)

   <table id="table_5E184F67CCEC4421B2BBD4261711A6FE"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Paramètre </th> 
      <th colname="col2" class="entry"> Description </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Heure de fin </td> 
      <td colname="col2"> <p>Facultatif. Filtrez les données pour inclure les entrées du journal avec horodatages jusqu’à cette heure, mais sans les inclure. Adobe recommande d’utiliser l’un des formats suivants pour l’heure : 
      <ul id="ul_1EC55DA4936946C98E447E1476E8280F"> 
       <li id="li_F2D862833F4B451C965E1ED6C05DCE1B"> 1er janvier 2013 HH:MM:SS EDT </li> 
       <li id="li_EB7FFEB2E2C24EAFB8E4B14F2479DA3D"> 1er janvier 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Par exemple, en spécifiant "29 juillet 2013 00:00:00 EDT" puisque l’heure de fin inclut les données jusqu’au 28 juillet 2013, à 11:59:59 HEURES HEURES. </p> <p> Vous devez spécifier un fuseau horaire. Le fuseau horaire n’est pas défini par défaut sur GMT s’il n’est pas spécifié. Pour obtenir la liste des abréviations de fuseaux horaires prises en charge par le serveur Data Workbench, voir <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codes du fuseau horaire </a>. </p> <p> <p>Remarque : Si vous spécifiez une valeur pour l’heure de fin, un paramètre nommé Heure de fin est défini et appliqué tout au long de la phase de transformation de la construction du jeu de données. Pour plus d’informations sur les paramètres, voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Définition des paramètres dans les fichiers d’inclusion de jeux de données </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dimensions étendues </td> 
      <td colname="col2"> Facultatif. Adobe recommande de définir des dimensions étendues dans une ou plusieurs dimensions <span class="wintitle"> Inclure le jeu de données de transformation </span> fichiers . Pour plus d’informations, voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Fichiers d’inclusion de jeux de données de transformation </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Seuil de hachage </td> 
      <td colname="col2"> <p>Facultatif. Facteur d’échantillonnage pour un sous-échantillonnage aléatoire de lignes. S’il est défini sur un nombre n, un seul identifiant de suivi sur chaque n entre dans le jeu de données, ce qui réduit le nombre total de lignes du jeu de données d’un facteur n. Pour créer un jeu de données qui nécessite une précision de 100 % (c’est-à-dire, pour inclure toutes les lignes), vous devez définir le seuil de hachage sur 1. </p> <p> Si le seuil de hachage est spécifié dans la variable <span class="filepath"> Log Processing.cfg </span> et <span class="filepath"> Transformation.cfg </span> fichiers, il n’est pas appliqué en séquence ; le nombre maximal de valeurs définies dans l’un ou l’autre des fichiers de configuration s’applique. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condition d’entrée du journal </td> 
      <td colname="col2"> Facultatif. Définit les règles selon lesquelles les entrées de journal générées par le traitement du journal sont prises en compte pour inclusion dans le profil du jeu de données. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condition d’entrée du journal </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nouvelle condition de visiteur </td> 
      <td colname="col2"> Facultatif. À utiliser avec les données web. Définit les règles selon lesquelles les visiteurs sont considérés comme pouvant être inclus dans les données. Le <span class="wintitle"> Nouvelle condition du visiteur </span> définit la première entrée de journal d’un visiteur (triée par heure) à utiliser dans le jeu de données. Toutes les entrées de journal suivantes de ce visiteur sont incluses dans le jeu de données, qu’elles respectent ou non cette condition. Voir <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3"> Nouvelle condition du visiteur </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Retraiter </td> 
      <td colname="col2"> <p>Facultatif. N’importe quel caractère ou combinaison de caractères peut être saisi ici. La modification de ce paramètre et l’enregistrement du fichier initie la retransformation des données. </p> <p> Pour plus d’informations sur le retraitement de vos données, voir <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Retraitement et retransformation </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Vérification de schéma </td> 
      <td colname="col2"> True ou false. Si la valeur est true, le serveur Data Workbench identifie les problèmes de corruption des jeux de données et enregistre des informations sur les problèmes dans les fichiers journaux dans le répertoire Trace du serveur Data Workbench. La valeur par défaut est true. Adobe recommande de laisser ce paramètre défini sur true à tout moment. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Phases </td> 
      <td colname="col2"> <p>Facultatif. Les noms des étapes de traitement qui peuvent être utilisés dans <span class="wintitle"> Inclure le jeu de données de transformation </span> fichiers . Les étapes de traitement permettent d’organiser les transformations définies dans <span class="wintitle"> Inclure le jeu de données de transformation </span> fichiers . Ce paramètre est très utile si vous avez défini une ou plusieurs transformations dans plusieurs <span class="wintitle"> Inclure le jeu de données de transformation </span> et vous souhaitez que des transformations spécifiques soient effectuées à des moments spécifiques lors de la transformation. </p> <p> L’ordre dans lequel vous répertoriez les scènes détermine l’ordre dans lequel les transformations dans la <span class="wintitle"> Inclure le jeu de données de transformation </span> sont exécutés pendant la transformation. <span class="wintitle"> Prétraitement </span> et <span class="wintitle"> Post-traitement </span> sont des phases intégrées; <span class="wintitle"> Prétraitement </span> est toujours la première étape, et <span class="wintitle"> Post-traitement </span> est toujours la dernière étape. Par défaut, il existe une scène nommée <span class="wintitle"> Par défaut </span>. </p> <p> <b>Pour ajouter une nouvelle étape de traitement</b> </p> <p> 
      <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
       <li id="li_80627E7A89CE4E57A4228C4F5496533F"> Dans le <span class="filepath"> Transformation.cfg </span> fenêtre, clic droit <span class="uicontrol"> Phases </span> et cliquez sur <span class="uicontrol"> Ajouter </span> &gt; <span class="uicontrol"> Évaluation </span>. </li> 
       <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> Saisissez le nom de la nouvelle étape. </li> 
      </ul> </p> <p> <b>Pour supprimer une étape de traitement existante</b> </p> <p> 
      <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
       <li id="li_3B3829DA34FD4774B3F9F94074099794"> Cliquez avec le bouton droit de la souris sur le nombre correspondant à l’étape que vous souhaitez supprimer, puis cliquez sur <span class="uicontrol"> Supprimer </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>Remarque : Lorsque vous spécifiez une étape dans une <span class="wintitle"> Inclure le jeu de données de transformation </span> fichiers le nom de l’étape doit correspondre exactement au nom que vous saisissez ici. Pour plus d’informations sur les fichiers d’inclusion de jeux de données, voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Fichiers d’inclusion de jeux de données </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Heure de début </td> 
      <td colname="col2"> <p>Facultatif. Filtrez les données pour inclure les entrées du journal avec horodatages à cette heure ou après cette heure. Adobe recommande d’utiliser l’un des formats suivants pour l’heure : 
      <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
       <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> 1er janvier 2013 HH:MM:SS EDT </li> 
       <li id="li_CA1BB675C1244104915FB9ED96A3013D"> 1er janvier 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Par exemple, en spécifiant le 29 juillet 2013 00:00:00 EDT comme le <span class="wintitle"> Heure de début </span> inclut des données à partir du 29 juillet 2013, au 12:00:00H00 HNE. </p> <p> Vous devez spécifier un fuseau horaire. Le fuseau horaire n’est pas défini par défaut sur GMT s’il n’est pas spécifié. Pour obtenir la liste des abréviations de fuseau horaire prises en charge par le serveur Data Workbench, voir <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codes du fuseau horaire </a>. </p> <p> <p>Remarque : Si vous spécifiez une valeur pour l’heure de début, un paramètre nommé Heure de début est défini et appliqué tout au long de la phase de transformation de la construction du jeu de données. Pour plus d’informations sur les paramètres, voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Définition des paramètres dans les fichiers d’inclusion de jeux de données </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformations </td> 
      <td colname="col2"> Facultatif. Adobe recommande de définir des transformations pour la phase de transformation de la construction d’un jeu de données dans un ou plusieurs jeux de données. <span class="wintitle"> Inclure le jeu de données de transformation </span> fichiers . Pour plus d’informations, voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Fichiers d’inclusion de jeux de données de transformation </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fuseau horaire </td> 
      <td colname="col2"> <p>Fuseau horaire du profil du jeu de données. Les fuseaux horaires sont utilisés pour les conversions horaires et pour la création de dimensions temporelles. Voir <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fuseaux horaires </a>. </p> <p> <p>Remarque : Lorsqu’elle est définie dans la variable <span class="filepath"> Log Processing.cfg </span> , le paramètre Fuseau horaire est utilisé pour les conversions temporelles uniquement. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
1. Dans le [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche pour [!DNL Transformation.cfg]dans le [!DNL User] , puis cliquez sur **[!UICONTROL Save to]** > * **[!UICONTROL dataset profile name]** pour que les modifications apportées localement prennent effet. La retransformation des données commence après la synchronisation du profil du jeu de données.

   >[!NOTE]
   >
   >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.

   Pour plus d’informations sur le retraitement ou la transformation de vos données, voir [Retraitement et retransformation](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
