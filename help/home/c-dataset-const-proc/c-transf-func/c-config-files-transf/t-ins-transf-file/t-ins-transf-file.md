---
description: Le fichier Data WorkbenchTransform.cfg contient les paramètres qui définissent les sources de journaux, les transformations de données et les exportateurs.
title: Le fichier Transform.cfg
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
exl-id: e84f2536-cb22-4c47-a7a8-270b3c37ece6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1336'
ht-degree: 2%

---

# Le fichier Transform.cfg{#the-transform-cfg-file}

Le fichier Data WorkbenchTransform.cfg contient les paramètres qui définissent les sources de journaux, les transformations de données et les exportateurs.

Les transformations que vous définissez manipulent les données brutes collectées par les capteurs (fichiers [!DNL .vsl]) ou contenues dans des fichiers texte, des fichiers XML ou des bases de données conformes à ODBC et les génèrent soit dans des champs existants, en remplaçant les données actives, soit dans des champs nouvellement définis.

Pour configurer la fonctionnalité de transformation, vous modifiez le fichier Data Workbench [!DNL Transform.cfg] dans le dossier Jeu de données pour le profil pour lequel vous souhaitez exporter les données d’événement. En règle générale, ce profil est dédié à la fonctionnalité de transformation (c’est-à-dire que vous n’effectuez aucun traitement de données autre que celui défini dans le fichier [!DNL Transform.cfg] Data Workbench). Il est important de noter que toutes les instructions de traitement spécifiées dans les fichiers [!DNL Log Processing Dataset Include] pour tous les profils hérités sont appliquées en plus de celles spécifiées dans le fichier [!DNL Transform.cfg] Data Workbench.

Pour plus d’informations sur les fichiers d’inclusion de jeux de données, voir [Fichiers d’inclusion de jeux de données](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Si les données que vous souhaitez exporter sont traitées par une grappe de serveurs Data Workbench, chacun des serveurs de traitement (DPU) de la grappe traite les données, mais seul le premier DPU (serveur de traitement #0 dans le fichier [!DNL profile.cfg]) écrira les données de sortie dans son système de fichiers local.

**Pour modifier le fichier Transform.cfg de Data Workbench**

1. Lorsque vous travaillez dans le profil pour lequel vous souhaitez exporter des données, ouvrez [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour afficher le contenu du répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche en regard de Data Workbench [!DNL Transform.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La fenêtre Data Workbench [!DNL Transform.cfg] s’affiche.
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
    <td colname="col2"> <p>Facultatif. Filtrez les données pour inclure les entrées du journal avec horodatages jusqu’à cette heure, mais sans les inclure. Adobe recommande d’utiliser l’un des formats suivants pour l’heure : 
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> 1er janvier 2013HH:MM:SS EDT </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> 1er janvier 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Par exemple, la spécification du 29 juillet 2013 00:00:00 EDT comme <span class="wintitle"> Heure de fin </span> inclut des données jusqu’au 28 juillet 2013, à 11:59:59 PM EDT. </p> <p> Vous devez spécifier un fuseau horaire. Le fuseau horaire n’est pas défini par défaut sur GMT s’il n’est pas spécifié. Pour obtenir la liste des abréviations de fuseau horaire prises en charge par le serveur Data Workbench, voir <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codes de fuseau horaire </a>. </p> <p> Le paramètre Utiliser les heures de début et de fin pour les sources de fichiers journaux et Capteur est associé à ce paramètre. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Exportateurs </td> 
    <td colname="col2"> <p>Les sous-champs d'un exportateur spécifient le mode de traitement et/ou de formatage des données de sortie. Vous pouvez définir plusieurs exportateurs pour un ensemble de sources de journal. Chaque type d’exportateur crée une sortie indépendamment. </p> <p> Il existe trois types d'exportateurs : 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> Pour plus d’informations sur les types d’exportateurs, voir <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> Définition des exportateurs </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Seuil de hachage </td> 
    <td colname="col2"> Facultatif. Facteur d’échantillonnage pour un sous-échantillonnage aléatoire de lignes. S’il est défini sur un nombre n, un seul identifiant de suivi sur chaque n est sélectionné pour l’exportation, ce qui réduit le nombre total de lignes exportées par un facteur n. Pour exporter toutes les lignes, définissez le Seuil de hachage sur 1. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Condition d’entrée du journal </td> 
    <td colname="col2"> Facultatif. Définit les règles selon lesquelles les entrées de journal sont prises en compte pour l’exportation. Pour plus d’informations sur la <span class="wintitle"> condition d’entrée du journal </span>, voir <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> fichier de configuration de traitement du journal </a>. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Sources de journalisation </td> 
    <td colname="col2"> <p>Sources des données. <span class="wintitle"> Les sources de journal  </span> peuvent être des  <span class="filepath">   </span> fichiers .vsl, des fichiers journaux ou des fichiers XML ou des données provenant de bases de données compatibles avec ODBC. Pour plus d’informations sur <span class="wintitle"> sources de journal </span>, voir <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Fichier de configuration de traitement du journal </a>. </p> <p> <span class="wintitle"> Transform  </span> s’attend à ce que toutes les données source soient dans l’ordre chronologique au sein de fichiers d’entrée triés lexicographiquement. Si cette exigence n’est pas satisfaite, les calculs "À partir de" sont incorrects et des données d’entrée supplémentaires peuvent être traitées après la fermeture des fichiers de sortie. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Mode hors ligne </td> 
    <td colname="col2"> <p>Facultatif. Vrai ou faux. Si la valeur est true, <span class="wintitle"> Transform </span> suppose que tous les fichiers d’entrée sont présents lorsqu’il commence à traiter les données. Une fois toutes les données d’entrée lues, <span class="wintitle"> Transform </span> ferme tous les fichiers de sortie sans attendre que des données supplémentaires soient reçues. La valeur par défaut est false. </p> <p> <p>Remarque :  Si <span class="wintitle"> Mode hors ligne </span> est défini sur true, <span class="wintitle"> Transform </span> s’attend à ce que toutes les données source soient présentes avant le début du traitement. Un message d’avertissement est généré dans le fichier <span class="filepath"> VisualServer.log </span> si des données supplémentaires sont reçues une fois les fichiers de sortie fermés. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Retraiter </td> 
    <td colname="col2"> <p>Facultatif. N’importe quel caractère ou combinaison de caractères peut être saisi ici. La modification de ce paramètre et l’enregistrement du fichier sur la machine <span class="wintitle"> Transform </span> lance le retraitement des données. </p> <p> Pour plus d’informations sur le retraitement de vos données, voir <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Retraitement et retransformation </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Phases </td> 
    <td colname="col2"> <p>Facultatif. Les noms des étapes de traitement pouvant être utilisées dans le <span class="wintitle"> jeu de données de traitement du journal incluent les fichiers </span> qui sont exécutés en plus du fichier Data Workbench <span class="filepath"> Transform.cfg </span>. Les étapes de traitement permettent d’organiser les transformations définies dans les fichiers <span class="wintitle"> Jeu de données de traitement du journal contenant les fichiers </span>. Ce paramètre est très utile si vous avez défini une ou plusieurs transformations dans plusieurs fichiers <span class="wintitle"> Jeu de données de traitement du journal contenant </span> et que vous souhaitez que des transformations spécifiques soient effectuées à des moments spécifiques pendant le processus d’exportation. </p> <p> L’ordre dans lequel vous listez les étapes détermine l’ordre dans lequel les transformations des fichiers <span class="wintitle"> Jeu de données de traitement du journal (y compris </span>) sont exécutées lors de l’exportation des données. <span class="wintitle"> Le prétraitement  </span> et le  <span class="wintitle"> posttraitement  </span> sont des étapes intégrées ;  <span class="wintitle"> Le prétraitement  </span> est toujours la première étape et le  <span class="wintitle"> posttraitement  </span> est toujours la dernière étape. Par défaut, il existe une étape nommée <span class="wintitle"> Par défaut </span>. </p> <p> <b>Pour ajouter une nouvelle étape de traitement</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> Dans la fenêtre Data Workbench <span class="filepath"> Transform.cfg </span> , cliquez avec le bouton droit de la souris sur <span class="uicontrol"> Étapes </span>, puis cliquez sur <span class="uicontrol"> Ajouter </span> &gt; <span class="uicontrol"> Étape </span>. </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> Saisissez le nom de la nouvelle étape. </li> 
      </ul> <p> <b>Pour supprimer une étape de traitement existante</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> Cliquez avec le bouton droit de la souris sur le numéro correspondant à l’étape que vous souhaitez supprimer, puis cliquez sur <span class="uicontrol"> Supprimer </span><i>&lt; <span class="uicontrol"> #stage_number </span></i>. </li> 
      </ul> <p> <p>Remarque :  Lorsque vous spécifiez une étape dans un fichier <span class="wintitle"> Jeu de données de traitement du journal Inclure </span> , le nom de l’étape doit correspondre exactement au nom que vous saisissez ici. Pour plus d’informations sur les fichiers d’inclusion de jeux de données, voir <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Fichiers d’inclusion de jeux de données </a>. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Heure de début </td> 
    <td colname="col2"> <p>Facultatif. Filtrez les données pour inclure les entrées du journal avec horodatages à cette heure ou après cette heure. Adobe recommande d’utiliser l’un des formats suivants pour l’heure : </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 1er janvier 2013 HH:MM:SS EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 1er janvier 2013 HH:MM:SS GMT </li> 
      </ul> <p> Par exemple, la spécification du 29 juillet 2013 00:00:00 EDT comme heure de début inclut des données à partir du 29 juillet 2013, à 12:00:00 AM EDT. </p> <p> Vous devez spécifier un fuseau horaire. Le fuseau horaire n’est pas défini par défaut sur GMT s’il n’est pas spécifié. Pour obtenir la liste des abréviations de fuseau horaire prises en charge par le serveur Data Workbench, voir <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codes de fuseau horaire </a>. </p> <p> <p>Remarque :  Le paramètre Utiliser les heures de début et de fin pour les sources de fichiers journaux et Capteur est associé à ce paramètre. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Transformations </td> 
    <td colname="col2"> <p>Facultatif. Définit les transformations à appliquer aux données. Pour plus d’informations sur les types de transformation disponibles, voir <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Transformations de données </a>. </p> <p> <p>Remarque :  Les types de transformation suivants ne fonctionnent pas lorsqu’ils sont définis dans le fichier Data Workbench <span class="filepath"> Transform.cfg </span> : </p> </p> 
      <ul id="ul_B091DFBD1C33471BBC01AEC7E92FC8CC"> 
       <li id="li_660EBECFC407488199CCCC886326806D"> AppendURI </li> 
       <li id="li_56BCEBE4A2D044AE87F5B747C6501817"> CrossRows </li> 
       <li id="li_B23B4E81B37942DCA55FEC1A6239C5FA"> ODBCLookup </li> 
       <li id="li_EF0AFF13C40D4AB49EAB4EF1691F8FA4"> Sessionize </li> 
      </ul> </td> 
    </tr> 
  </tbody> 
  </table>

>[!NOTE]
>
>Si des données additionnelles sont reçues une fois les fichiers de sortie fermés (voir [!DNL Log Sources] et [!DNL Offline Mode] dans le tableau précédent), [!DNL Transform] crée de nouveaux fichiers de sortie avec les données additionnelles. Les noms des nouveaux fichiers de sortie sont générés à partir du nom du fichier de sortie d’origine avec l’ajout d’un numéro de version entre parenthèses juste avant l’extension. Par exemple, si le fichier de sortie d’origine est [!DNL 20070701-ABC.vsl], les versions suivantes de ce fichier seront nommées [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl], etc. Notez que l’utilisation des fichiers versionnés en tant qu’entrée au serveur Data Workbench peut entraîner des erreurs de traitement.
>
>
>Adobe recommande d’éviter la création de fichiers de sortie versionnés en s’assurant que toutes les données source sont dans l’ordre chronologique dans les fichiers d’entrée triés lexicographiquement et, si [!DNL Offline Mode] est défini sur true, que toutes les données source sont présentes avant le début du traitement. Pour plus d’informations, voir les entrées [!DNL Log Sources] et [!DNL Offline Mode] du tableau précédent.

1. Ajoutez des transformations en cliquant avec le bouton droit de la souris sur **[!UICONTROL Transformations]** et en cliquant sur **[!UICONTROL Add new]** > **[!UICONTROL Transformation type]**. Renseignez les champs de transformation.

   Voir [Transformations de données](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) pour obtenir des descriptions et des exemples des transformations que vous pouvez utiliser avec les fonctionnalités de transformation.

1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
1. Pour que les modifications apportées localement prennent effet, dans la balise [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche de Data Workbench [!DNL Transform.cfg] dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, où le nom du profil est le nom du profil pour lequel vous exportez des données. Le retraitement des données commence après la synchronisation du profil.

   >[!NOTE]
   >
   >Pour plus d’informations sur le retraitement de vos données à exporter, voir [Retraitement et retransformation](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
