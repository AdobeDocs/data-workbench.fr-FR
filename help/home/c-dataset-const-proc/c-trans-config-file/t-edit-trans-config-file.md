---
description: Etapes de modification du fichier Transformation.cfg pour un profil de jeu de données.
solution: Analytics
title: Modification du fichier de configuration de transformation
topic: Data workbench
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Modification du fichier de configuration de transformation{#editing-the-transformation-configuration-file}

Etapes de modification du fichier Transformation.cfg pour un profil de jeu de données.

1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez le fichier [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour en afficher le contenu.

   Pour plus d’informations sur l’ouverture et l’utilisation de [!DNL Profile Manager]Data Workbench, consultez le Guide *de l’utilisateur des outils de* données.

   >[!NOTE]
   >
   >Un sous-répertoire Transformation peut exister dans le répertoire des jeux de données. Ce sous-répertoire contient les [!DNL Transformation Dataset Include] fichiers créés pour un ou plusieurs profils hérités. Pour plus d’informations sur [!DNL Transformation Dataset Include] les fichiers, voir Fichiers [inclus dans le jeu de](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)données.

1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL Transformation.cfg] , puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la [!DNL User] colonne.
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. La [!DNL Transformation.cfg] fenêtre s&#39;affiche.

   Vous pouvez également ouvrir le [!DNL Transformation.cfg] fichier à partir d’un [!DNL Transformation Dependency Map]. Pour plus d’informations sur [!DNL transformation dependency maps]cette solution, voir Outils [de configuration des jeux de](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)données.

1. Modifiez les paramètres du fichier de configuration à l’aide du tableau suivant comme guide.

   Lors de la modification du [!DNL Transformation.cfg] fichier dans une fenêtre de l’outil de données, vous pouvez utiliser des touches de raccourci pour les fonctions de modification de base, notamment couper (Ctrl+x), copier (Ctrl+c), coller (Ctrl+v), annuler (Ctrl+z), rétablir (Ctrl+Maj+z), sélectionner une section (cliquer+faire glisser) et sélectionner tout (Ctrl+a). En outre, vous pouvez utiliser les raccourcis pour copier et coller le texte d’un fichier de configuration ( [!DNL .cfg]) vers un autre.

   >[!NOTE]
   >
   >Un [!DNL Transformation Dataset Include] fichier pour un profil hérité contient un sous-ensemble des paramètres décrits dans le tableau suivant, ainsi que quelques paramètres supplémentaires. Pour plus d’informations sur [!DNL Transformation Dataset Include] les fichiers, voir Fichiers [inclus dans le jeu de données](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)

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
      <td colname="col2"> <p>Facultatif. Filtrez les données afin d’inclure les entrées de journal avec horodatage jusqu’à cette heure, mais pas celle-ci. Adobe recommande d’utiliser l’un des formats suivants pour l’instant : 
      <ul id="ul_1EC55DA4936946C98E447E1476E8280F"> 
       <li id="li_F2D862833F4B451C965E1ED6C05DCE1B"> 1er janvier 2013 HH:MM:SS EDT </li> 
       <li id="li_EB7FFEB2E2C24EAFB8E4B14F2479DA3D"> 1er janvier 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Par exemple, la spécification de "29 juillet 2013 à 00:00:00 EDT" comme Heure de fin inclut les données jusqu’au 28 juillet 2013 à 11h59:59 HAE. </p> <p> Vous devez spécifier un fuseau horaire. Le fuseau horaire n’est pas défini par défaut sur GMT s’il n’est pas spécifié. Pour obtenir la liste des abréviations de fuseau horaire prises en charge par le serveur de l’outil de données, voir <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codes de fuseau horaire </a>. </p> <p> <p>Remarque :  Si vous spécifiez une valeur pour Heure de fin, un paramètre nommé Heure de fin est défini et appliqué tout au long de la phase de transformation de la construction du jeu de données. Pour plus d’informations sur les paramètres, voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Définition de paramètres dans le jeu de données Inclure des fichiers </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dimensions étendues </td> 
      <td colname="col2"> Facultatif. Adobe recommande de définir des dimensions étendues dans un ou plusieurs <span class="wintitle"> </span> fichiers d’inclusion de jeux de données de transformation. Pour plus d’informations, voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Jeu de données de transformation - Inclusion de fichiers </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Seuil de hachage </td> 
      <td colname="col2"> <p>Facultatif. Facteur d’échantillonnage pour le sous-échantillonnage aléatoire des lignes. S’il est défini sur un nombre n, un seul identifiant de suivi sur chaque n entre dans le jeu de données, réduisant le nombre total de lignes du jeu de données par un facteur n. Pour créer un jeu de données qui requiert une précision de 100 % (c'est-à-dire, inclure toutes les lignes), vous devez définir le seuil de hachage sur 1. </p> <p> Si le seuil de hachage est spécifié dans les fichiers <span class="filepath"> Log Processing.cfg </span> et <span class="filepath"> Transformation.cfg </span> , il n’est pas appliqué dans l’ordre. le maximum des valeurs définies dans l’un ou l’autre fichier de configuration s’applique. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condition d’entrée de journal </td> 
      <td colname="col2"> Facultatif. Définit les règles selon lesquelles les entrées de journal générées par le traitement du journal sont prises en compte pour l’inclusion dans le profil du jeu de données. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condition d’entrée dans le journal </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nouvelle condition du visiteur </td> 
      <td colname="col2"> Facultatif. Utilisation avec des données Web. Définit les règles selon lesquelles les visiteurs sont considérés comme pouvant être inclus dans les données. La <span class="wintitle"> nouvelle condition du visiteur </span> définit la première entrée de journal d’un visiteur (triée par heure) à utiliser dans le jeu de données. Toutes les entrées de journal suivantes pour ce visiteur sont incluses dans le jeu de données, qu’elles respectent ou non cette condition. Voir <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3"> Nouvelle condition du visiteur </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Retraiter </td> 
      <td colname="col2"> <p>Facultatif. Tout caractère ou combinaison de caractères peut être saisi ici. La modification de ce paramètre et l’enregistrement du fichier initient la retransformation des données. </p> <p> Pour plus d’informations sur le retraitement de vos données, voir <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Retraitement et retransformation </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Vérification de schéma </td> 
      <td colname="col2"> True ou false. Si la valeur est true, le serveur de l’outil de données identifie les problèmes de corruption des jeux de données et enregistre des informations sur les problèmes des fichiers journaux dans le répertoire de suivi du serveur de l’outil de données. La valeur par défaut est true. Adobe conseille de laisser ce paramètre défini sur true à tout moment. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Etapes </td> 
      <td colname="col2"> <p>Facultatif. Les noms des étapes de traitement pouvant être utilisées dans le jeu de données de <span class="wintitle"> transformation incluent </span> des fichiers. Les étapes de traitement permettent d’organiser les transformations définies dans les <span class="wintitle"> fichiers d’inclusion des jeux de données de </span> transformation. Ce paramètre s’avère très utile si vous avez défini une ou plusieurs transformations dans plusieurs fichiers d’inclusion de jeux de données de <span class="wintitle"> </span> transformation et que vous souhaitez que des transformations spécifiques soient effectuées à des moments spécifiques au cours de la transformation. </p> <p> L’ordre dans lequel vous dressez les étapes ici détermine l’ordre dans lequel les transformations dans les fichiers <span class="wintitle"> Transformation Data Inclure </span> sont exécutées au cours de la transformation. <span class="wintitle"> Le prétraitement </span> et le <span class="wintitle"> posttraitement </span> sont des étapes intégrées; <span class="wintitle"> Le prétraitement </span> est toujours la première étape et le <span class="wintitle"> posttraitement </span> est toujours la dernière étape. Par défaut, il existe une scène nommée <span class="wintitle"> Par défaut </span>. </p> <p> <b>Pour ajouter une nouvelle étape de traitement</b> </p> <p> 
      <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
       <li id="li_80627E7A89CE4E57A4228C4F5496533F"> Dans la fenêtre <span class="filepath"> Transformation.cfg </span> , cliquez avec le bouton droit de la souris sur <span class="uicontrol"> Etapes </span> et cliquez sur <span class="uicontrol"> Ajouter nouveau </span> &gt; <span class="uicontrol">  d’étape.</span> </li> 
       <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> Entrez le nom de la nouvelle étape. </li> 
      </ul> </p> <p> <b>Pour supprimer une étape de traitement existante</b> </p> <p> 
      <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
       <li id="li_3B3829DA34FD4774B3F9F94074099794"> Cliquez avec le bouton droit de la souris sur le numéro correspondant à l’étape à supprimer, puis cliquez sur <span class="uicontrol"> Supprimer </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>Remarque :  Lorsque vous spécifiez une étape dans un <span class="wintitle"> jeu de données de transformation Inclure </span> les fichiers, le nom de l’étape doit correspondre exactement au nom que vous saisissez ici. Pour plus d’informations sur les fichiers d’inclusion d’un jeu de données, voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Jeu de données - Inclure des fichiers </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Heure de début </td> 
      <td colname="col2"> <p>Facultatif. Filtrez les données pour inclure les entrées de journal avec horodatage à cette heure ou après. Adobe recommande d’utiliser l’un des formats suivants pour l’instant : 
      <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
       <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> 1er janvier 2013 HH:MM:SS EDT </li> 
       <li id="li_CA1BB675C1244104915FB9ED96A3013D"> 1er janvier 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Par exemple, la spécification du 29 juillet 2013 à 00:00:00 EDT comme Heure de <span class="wintitle"> début </span> inclut des données commençant le 29 juillet 2013 à 12:00:00 EDT. </p> <p> Vous devez spécifier un fuseau horaire. Le fuseau horaire n’est pas défini par défaut sur GMT s’il n’est pas spécifié. Pour obtenir la liste des abréviations de fuseau horaire prises en charge par le serveur de l’outil de données, voir <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codes de fuseau horaire </a>. </p> <p> <p>Remarque :  Si vous spécifiez une valeur pour Heure de début, un paramètre nommé Heure de début est défini et appliqué tout au long de la phase de transformation de la construction du jeu de données. Pour plus d’informations sur les paramètres, voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Définition de paramètres dans le jeu de données Inclure des fichiers </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformations </td> 
      <td colname="col2"> Facultatif. Adobe recommande de définir les transformations de la phase de transformation de la construction d’un jeu de données dans un ou plusieurs <span class="wintitle"> fichiers d’inclusion de jeux de données de transformation </span> . Pour plus d’informations, voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Jeu de données de transformation - Inclusion de fichiers </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fuseau horaire </td> 
      <td colname="col2"> <p>Fuseau horaire du profil du jeu de données. Les fuseaux horaires sont utilisés pour les conversions temporelles et pour la création de dimensions temporelles. Voir <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fuseaux horaires </a>. </p> <p> <p>Remarque :  Lorsqu’il est défini dans le fichier <span class="filepath"> Log Processing.cfg </span> , le paramètre Fuseau horaire est utilisé uniquement pour les conversions temporelles. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.
1. Dans la [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL Transformation.cfg]dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > * **[!UICONTROL dataset profile name]** pour que les modifications apportées localement prennent effet. La retransformation des données commence après la synchronisation du profil du jeu de données.

   >[!NOTE]
   >
   >N’enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

   Pour plus d’informations sur le retraitement ou la transformation de vos données, voir [Retraitement et retransformation](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
