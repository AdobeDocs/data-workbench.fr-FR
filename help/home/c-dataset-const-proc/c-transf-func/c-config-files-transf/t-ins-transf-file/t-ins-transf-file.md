---
description: Le fichier data workbenchTransform.cfg contient les paramètres qui définissent les sources du journal, les transformations de données et les exportateurs.
solution: Analytics
title: Le fichier Transform.cfg
topic: Data workbench
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Le fichier Transform.cfg{#the-transform-cfg-file}

Le fichier data workbenchTransform.cfg contient les paramètres qui définissent les sources du journal, les transformations de données et les exportateurs.

Les transformations que vous définissez manipulent les données brutes collectées par Sensors ( [!DNL .vsl] fichiers) ou contenues dans des fichiers texte, des fichiers XML ou des bases de données conformes ODBC et les génèrent soit dans des champs existants, en écrasant les données actives, soit dans des champs nouvellement définis.

Pour configurer la fonctionnalité de transformation, vous modifiez le [!DNL Transform.cfg] fichier des outils de données dans le dossier Jeu de données pour le profil pour lequel vous souhaitez exporter les données d’événement. En règle générale, ce profil est dédié à la fonctionnalité de transformation (c’est-à-dire que vous n’effectuez aucun autre traitement de données que celui défini dans le [!DNL Transform.cfg] fichier de l’outil de données). Il est important de noter que toutes les instructions de traitement spécifiées dans les [!DNL Log Processing Dataset Include] fichiers pour les profils hérités sont appliquées en plus de celles spécifiées dans le [!DNL Transform.cfg] fichier de l’outil de données.

Pour plus d’informations sur les fichiers d’inclusion de jeux de données, voir Fichiers [inclus dans les jeux de](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)données.

Si les données que vous souhaitez exporter sont traitées par une grappe de serveurs de outils de données, chacun des serveurs de traitement (DPU) de la grappe traite les données, mais seul le premier DPU (serveur de traitement n° 0 dans le [!DNL profile.cfg] fichier) écrit les données de sortie dans son système de fichiers local.

**Pour modifier le fichier Transform.cfg de l’outil de données**

1. Lorsque vous travaillez dans le profil pour lequel vous souhaitez exporter des données, ouvrez le fichier [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour afficher le contenu du répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche en regard de l’outil de données [!DNL Transform.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la [!DNL User] colonne.
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La fenêtre Outils de données [!DNL Transform.cfg] s’affiche.
1. Modifiez les paramètres du fichier de configuration à l’aide du tableau ci-dessous comme guide :

<table id="table_91D9C4C1BE2E43158D9D06C6284EE3C7"> 
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
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> 1er janvier 2013HH:MM:SS EDT </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> 1er janvier 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Par exemple, la spécification du 29 juillet 2013 à 00:00:00 EDT comme Heure de fin <span class="wintitle"> </span> inclut les données jusqu’au 28 juillet 2013 à 11h59:59 HAE. </p> <p> Vous devez spécifier un fuseau horaire. Le fuseau horaire n’est pas défini par défaut sur GMT s’il n’est pas spécifié. Pour obtenir la liste des abréviations de fuseau horaire prises en charge par le serveur de l’outil de données, voir <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codes de fuseau horaire </a>. </p> <p> Le paramètre Utiliser les heures de début et de fin pour les sources de fichiers journaux et Sensor est associé à ce paramètre. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Exportateurs </td> 
    <td colname="col2"> <p>Les sous-champs d’un exportateur indiquent comment les données de sortie sont traitées et/ou formatées. Vous pouvez définir plusieurs exportateurs pour un ensemble de sources de journal. Chaque type d’exportateur crée une sortie indépendante. </p> <p> Il existe trois types d'exportateurs : 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> Pour plus d’informations sur les types d’exportateurs, voir <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> Définition des exportateurs </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Seuil de hachage </td> 
    <td colname="col2"> Facultatif. Facteur d’échantillonnage pour le sous-échantillonnage aléatoire des lignes. S’il est défini sur le nombre n, seul un ID de suivi sur n est sélectionné pour l’exportation, ce qui réduit le nombre total de lignes exportées par un facteur n. Pour exporter toutes les lignes, définissez le seuil de hachage sur 1. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Condition d’entrée de journal </td> 
    <td colname="col2"> Facultatif. Définit les règles selon lesquelles les entrées de journal sont prises en compte pour l’exportation. Pour plus d’informations sur la condition d’entrée du <span class="wintitle"> journal </span>, voir Fichier de configuration de traitement du <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> journal </a>. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Sources de journal </td> 
    <td colname="col2"> <p>Sources de données. <span class="wintitle"> Les sources du journal </span> peuvent être <span class="filepath"> des fichiers .vsl </span> , des fichiers journaux ou des fichiers XML ou des données provenant de bases de données compatibles ODBC. Pour plus d’informations sur les sources de <span class="wintitle"> journaux </span>, voir Fichier de configuration de traitement des <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> journaux </a>. </p> <p> <span class="wintitle"> Transform </span> s’attend à ce que toutes les données source soient dans l’ordre chronologique au sein des fichiers d’entrée lexicographiques. Si cette exigence n’est pas satisfaite, les calculs sont incorrects et des données d’entrée supplémentaires peuvent être traitées après la fermeture des fichiers de sortie. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Mode hors ligne </td> 
    <td colname="col2"> <p>Facultatif. True ou false. Si la valeur est true, <span class="wintitle"> Transform </span> suppose que tous les fichiers d’entrée sont présents au démarrage du traitement des données. Lorsque toutes les données d’entrée ont été lues, <span class="wintitle"> Transform </span> ferme tous les fichiers de sortie sans attendre la réception de données supplémentaires. La valeur par défaut est false. </p> <p> <p>Remarque :  Si le mode <span class="wintitle"> hors ligne </span> est défini sur true, <span class="wintitle"> Transform </span> s’attend à ce que toutes les données source soient présentes avant le début du traitement. Un message d’avertissement est généré dans le fichier <span class="filepath"> VisualServer.log </span> si des données supplémentaires sont reçues après la fermeture des fichiers de sortie. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Retraiter </td> 
    <td colname="col2"> <p>Facultatif. Tout caractère ou combinaison de caractères peut être saisi ici. La modification de ce paramètre et l’enregistrement du fichier sur l’ordinateur <span class="wintitle"> Transform </span> initialise le retraitement des données. </p> <p> Pour plus d’informations sur le retraitement de vos données, voir <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Retraitement et retransformation </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Etapes </td> 
    <td colname="col2"> <p>Facultatif. Les noms des étapes de traitement qui peuvent être utilisées dans le jeu de données de traitement des <span class="wintitle"> journaux incluent </span> les fichiers exécutés en plus du fichier Transform.cfg <span class="filepath"> </span> de l’outil de données. Les étapes de traitement permettent d’organiser les transformations définies dans les fichiers Inclure <span class="wintitle"> les jeux de données de traitement du </span> journal. Ce paramètre est très utile si vous avez défini une ou plusieurs transformations dans plusieurs <span class="wintitle"> fichiers de données de traitement du journal Inclure </span> des fichiers et si vous souhaitez que des transformations spécifiques soient effectuées à des moments spécifiques pendant le processus d'exportation. </p> <p> L’ordre dans lequel vous dressez les étapes ici détermine l’ordre dans lequel les transformations dans le <span class="wintitle"> jeu de données de traitement du journal Inclure </span> les fichiers sont exécutées lors de l’exportation des données. <span class="wintitle"> Le prétraitement </span> et le <span class="wintitle"> posttraitement </span> sont des étapes intégrées; <span class="wintitle"> Le prétraitement </span> est toujours la première étape et le <span class="wintitle"> posttraitement </span> est toujours la dernière étape. Par défaut, il existe une scène nommée <span class="wintitle"> Par défaut </span>. </p> <p> <b>Pour ajouter une nouvelle étape de traitement</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> Dans la fenêtre <span class="filepath"> Transform.cfg de l’outil de données </span> , cliquez avec le bouton droit de la souris sur <span class="uicontrol"> Etapes </span>, puis cliquez sur <span class="uicontrol"> Ajouter nouveau </span> &gt; <span class="uicontrol">  d’étape.</span> </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> Entrez le nom de la nouvelle étape. </li> 
      </ul> <p> <b>Pour supprimer une étape de traitement existante</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> Cliquez avec le bouton droit de la souris sur le numéro correspondant à l’étape à supprimer, puis cliquez sur <span class="uicontrol"> Supprimer </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> <p> <p>Remarque :  Lorsque vous spécifiez une étape dans un <span class="wintitle"> fichier Jeu de données de traitement du journal Inclure </span> , le nom de l’étape doit correspondre exactement au nom que vous saisissez ici. Pour plus d’informations sur les fichiers d’inclusion d’un jeu de données, voir <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Jeu de données - Inclure des fichiers </a>. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Heure de début </td> 
    <td colname="col2"> <p>Facultatif. Filtrez les données pour inclure les entrées de journal avec horodatage à cette heure ou après. Adobe recommande d’utiliser l’un des formats suivants pour l’instant : </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 1er janvier 2013 HH:MM:SS EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 1er janvier 2013 HH:MM:SS GMT </li> 
      </ul> <p> Par exemple, la spécification du 29 juillet 2013 à 00:00:00 EDT comme Heure de début inclut les données à partir du 29 juillet 2013 à 12:00:00 EDT. </p> <p> Vous devez spécifier un fuseau horaire. Le fuseau horaire n’est pas défini par défaut sur GMT s’il n’est pas spécifié. Pour obtenir la liste des abréviations de fuseau horaire prises en charge par le serveur de l’outil de données, voir <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codes de fuseau horaire </a>. </p> <p> <p>Remarque :  Le paramètre Utiliser les heures de début et de fin pour les sources de fichiers journaux et Sensor est associé à ce paramètre. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Transformations </td> 
    <td colname="col2"> <p>Facultatif. Définit les transformations à appliquer aux données. Pour plus d’informations sur les types de transformation disponibles, voir <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Data Transformations </a>. </p> <p> <p>Remarque :  Les types de transformation suivants ne fonctionnent pas lorsqu’ils sont définis dans le fichier <span class="filepath"> Transform.cfg de l’outil de données </span> : </p> </p> 
      <ul id="ul_B091DFBD1C33471BBC01AEC7E92FC8CC"> 
       <li id="li_660EBECFC407488199CCCC886326806D"> AppendURI </li> 
       <li id="li_56BCEBE4A2D044AE87F5B747C6501817"> CrossRows </li> 
       <li id="li_B23B4E81B37942DCA55FEC1A6239C5FA"> ODBCLookup </li> 
       <li id="li_EF0AFF13C40D4AB49EAB4EF1691F8FA4"> Sessioniser </li> 
      </ul> </td> 
    </tr> 
  </tbody> 
  </table>

>[!NOTE]
>
>Si des données supplémentaires sont reçues après la fermeture des fichiers de sortie (voir [!DNL Log Sources] et [!DNL Offline Mode] dans le tableau précédent), [!DNL Transform] crée de nouveaux fichiers de sortie avec les données supplémentaires. Les noms des nouveaux fichiers de sortie sont générés à partir du nom du fichier de sortie d’origine avec l’ajout d’un numéro de version entre parenthèses juste avant l’extension. Par exemple, si le fichier de sortie original est [!DNL 20070701-ABC.vsl], les versions suivantes de ce fichier seront nommées [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl], etc. Notez que l’utilisation des fichiers avec version comme entrée au serveur de l’outil de données peut entraîner des erreurs de traitement.
>
>
>Adobe recommande d’éviter la création de fichiers de sortie avec version en s’assurant que toutes les données source sont dans l’ordre chronologique dans les fichiers d’entrée lexicographiques et, si la valeur [!DNL Offline Mode] est true, que toutes les données source sont présentes avant le début du traitement. Pour plus d’informations, voir les [!DNL Log Sources] entrées et les [!DNL Offline Mode] entrées du tableau précédent.

1. Ajoutez des transformations en cliquant avec le bouton droit **[!UICONTROL Transformations]** et en cliquant sur **[!UICONTROL Add new]** > **[!UICONTROL Transformation type]**. Renseignez les champs de transformation.

   Voir Transformations [de](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) données pour obtenir des descriptions et des exemples des transformations que vous pouvez utiliser avec la fonctionnalité de transformation.

1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
1. Pour que les modifications apportées localement prennent effet, dans la [!DNL Profile Manager]colonne, cliquez avec le bouton droit de la souris sur la coche de l’outil de données [!DNL Transform.cfg] dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, où nom du profil est le nom du profil pour lequel vous exportez des données. Le retraitement des données commence après la synchronisation du profil.

   >[!NOTE]
   >
   >Pour plus d’informations sur le retraitement de vos données pour l’exportation, voir [Retraitement et retransformation](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).