---
description: Procédure de modification du fichier Log Processing.cfg pour un profil de jeu de données.
title: Modification du fichier de configuration de traitement du journal
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
exl-id: 294063ef-6771-4310-8198-df57fab1e2b4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1284'
ht-degree: 2%

---

# Modification du fichier de configuration de traitement du journal{#editing-the-log-processing-configuration-file}

{{eol}}

Procédure de modification du fichier Log Processing.cfg pour un profil de jeu de données.

1. Lorsque vous travaillez dans votre profil de jeu de données, ouvrez la variable [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour afficher son contenu.

   Pour plus d’informations sur l’ouverture et l’utilisation de la variable [!DNL Profile Manager], reportez-vous à la section *Guide de l’utilisateur de Data Workbench*.

   >[!NOTE]
   >
   >Un sous-répertoire de traitement du journal peut exister dans le répertoire du jeu de données. Ce sous-répertoire contient la variable [!DNL Log Processing Dataset Include] fichiers créés pour un ou plusieurs profils hérités. Voir [Fichiers d’inclusion de jeux de données](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL Log Processing.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la variable [!DNL User] colonne .
1. Cliquez avec le bouton droit de la souris sur la coche que vous venez de créer, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. Le [!DNL Log Processing.cfg] s’affiche.

   Vous pouvez également ouvrir le [!DNL Log Processing.cfg] à partir d’un fichier [!DNL Transformation Dependency Map]. Pour plus d’informations sur les mappages des dépendances de transformation, voir [Outils de configuration des jeux de données](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. Editez les paramètres du fichier de configuration à partir du tableau suivant comme guide.

   Lors de la modification de la variable [!DNL Log Processing.cfg] dans une fenêtre Data Workbench, vous pouvez utiliser des raccourcis clavier pour les fonctions d’édition de base, notamment couper ( Ctrl+x ), copier ( Ctrl+c) , coller ( Ctrl+v ), annuler ( Ctrl+z ), rétablir ( Ctrl+Maj+z ), sélectionner une section (cliquer+faire glisser) et tout sélectionner ( Ctrl+a ). Vous pouvez également utiliser les raccourcis pour copier et coller le texte d’un fichier de configuration ( [!DNL .cfg]) à un autre.

   >[!NOTE]
   >
   >A [!DNL Log Processing Dataset Include] pour un profil hérité contient un sous-ensemble des paramètres décrits dans le tableau suivant, ainsi que certains paramètres supplémentaires. Voir [Fichiers d’inclusion de jeux de données](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

   <table id="table_BC7D3635C94049A9B608463AC1DBFA69">
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Paramètre </th> 
      <th colname="col2" class="entry"> Description </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Sources de journalisation </td> 
      <td colname="col2"> Sources des données. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Sources de journalisation </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Heure de fin </td> 
      <td colname="col2"> <p>Facultatif. Filtrez les données pour inclure les entrées du journal avec horodatages jusqu’à cette heure, sans inclure cette heure. Adobe recommande d’utiliser l’un des formats suivants pour l’heure : </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">1er janvier 2013 HH:MM:SS EDT </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">1er janvier 2013 HH:MM:SS GMT </li> 
      </ul> <p>Par exemple, en spécifiant le 29 juillet 2013 00:00:00 HNE car l’heure de fin inclut les données jusqu’au 28 juillet 2013, à 11:59:59 HEURES HEURES. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtres de données </a>. </p> <p>Vous devez spécifier un fuseau horaire. Le fuseau horaire n’est pas défini par défaut sur GMT s’il n’est pas spécifié. Pour obtenir la liste des abréviations de fuseaux horaires prises en charge par le serveur Data Workbench, voir <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codes du fuseau horaire </a>. </p> <p> <p>Remarque : Le paramètre Utiliser les heures de début et de fin pour <span class="wintitle"> Sensor </span>, le fichier journal et les sources XML sont associés à ce paramètre. Voir les sections de <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Sources de journalisation </a> qui abordent ces types de sources. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Champs </td> 
      <td colname="col2"> Facultatif. Adobe recommande de définir <span class="wintitle"> Champs </span> dans une ou plusieurs <span class="wintitle"> Inclure le jeu de données de traitement du journal </span> fichiers . Voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Fichiers d’inclusion de jeux de données de traitement journaux </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nombre maximal d’octets de clé du groupe </td> 
      <td colname="col2"> <p>Nombre maximal de données d’événement que le serveur peut traiter pour un seul ID de suivi. Les données dépassant cette limite sont filtrées à partir du processus de construction du jeu de données. Cette valeur doit être définie sur 2e6 lorsque le fractionnement de clé est principal et 1e6 lorsque le fractionnement de clé n’est pas principal. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Fractionnement des clés </a>. </p> <p> <p>Remarque : Ne modifiez pas cette valeur sans Adobe de conseil. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Seuil de hachage </td> 
      <td colname="col2"> <p>Facultatif. Facteur d’échantillonnage pour un sous-échantillonnage aléatoire de lignes. S’il est défini sur un nombre n, un seul identifiant de suivi sur chaque n entre dans le jeu de données, ce qui réduit le nombre total de lignes du jeu de données d’un facteur n. </p> <p>Pour créer un jeu de données qui nécessite une précision de 100 % (c’est-à-dire, pour inclure toutes les lignes), vous devez définir le seuil de hachage sur 1. </p> <p>Valeurs: </p> <span class="filepath"> Seuil de hachage = 1 </span> (100 % des données, y compris toutes les lignes). <p> <span class="filepath"> Seuil de hachage = 2 </span> (1/2 de données et comprend la moitié des lignes.) </p> <p> <span class="filepath"> Seuil de hachage = 3 </span>(1/3 de données et comprend une des trois lignes, mais arrondit à 34 % dans l’exécution de la requête) </p> <p> <span class="filepath"> Seuil de hachage = 4 </span>(1/4 de données et comprend une ligne sur quatre.) </p> <p> </p> <p> <p>Remarque : Utilisation d’un <span class="filepath"> Seuil de hachage = 8 </span> fournit 1/8 des données, soit 12,5 %. Cependant, la variable <span class="uicontrol"> Fin de requête </span> dans arrondit à 13 % pour cette valeur. D’autres exemples incluent <span class="filepath"> Seuil de hachage = 6 </span> qui donne une résolution de requête de 17 %. A <span class="filepath"> Seuil de hachage = 13 </span>donne une résolution de requête de 8 %. </p> </p> <p>If <span class="wintitle"> Seuil de hachage </span> est spécifié dans la variable <span class="filepath"> Log Processing.cfg </span> et <span class="filepath"> Transformation.cfg </span> fichiers, il n’est pas appliqué en séquence ; la valeur maximale définie dans l’un des fichiers de configuration s’applique. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtres de données </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condition d’entrée du journal </td> 
      <td colname="col2"> Facultatif. Définit les règles selon lesquelles les entrées de journal sont prises en compte pour inclusion dans le jeu de données. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condition d’entrée du journal </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Retraiter </td> 
      <td colname="col2"> <p>Facultatif. N’importe quel caractère ou combinaison de caractères peut être saisi ici. La modification de ce paramètre et l’enregistrement du fichier sur l’ordinateur du serveur Data Workbench entraîne le retraitement des données. </p> <p>Voir <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Retraitement et retransformation </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Split Key Bucket Space </td> 
      <td colname="col2"> <p>Paramètre impliqué dans le fractionnement des clés. Sa valeur doit être 6e6 lorsque le fractionnement de clé est principal. Voir <a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split"> Fractionnement des clés </a>. </p> <p> <p>Remarque : Ne modifiez pas cette valeur sans Adobe de conseil. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fractionner les octets clés </td> 
      <td colname="col2"> <p>Paramètre impliqué dans le fractionnement des clés. Sa valeur doit être 1e6 lorsque le fractionnement de clé est principal et 0 lorsque le fractionnement de clé n’est pas principal. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Fractionnement des clés </a>. </p> <p> <p>Remarque : Ne modifiez pas cette valeur sans Adobe de conseil. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Split Key Space Ratio </td> 
      <td colname="col2"> <p>Paramètre impliqué dans le fractionnement des clés. Sa valeur doit être 10 lorsque le fractionnement de clé est principal. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Fractionnement des clés </a>. </p> <p> <p>Remarque : Ne modifiez pas cette valeur sans Adobe de conseil. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Phases </td> 
      <td colname="col2"> <p>Facultatif. Les noms des étapes de traitement qui peuvent être utilisés dans <span class="wintitle"> Inclure le jeu de données de traitement du journal </span> fichiers . Les étapes de traitement permettent d’organiser les transformations définies dans <span class="wintitle"> Inclure le jeu de données de traitement du journal </span> fichiers . Ce paramètre est très utile si vous avez défini une ou plusieurs transformations dans plusieurs <span class="wintitle"> Inclure le jeu de données de traitement du journal </span> et vous souhaitez que des transformations spécifiques soient effectuées à des moments spécifiques pendant le traitement du journal. </p> <p>L’ordre dans lequel vous répertoriez les scènes détermine l’ordre dans lequel les transformations dans la <span class="wintitle"> Inclure le jeu de données de traitement du journal </span> Les fichiers sont exécutés pendant le traitement des journaux. Le prétraitement et le post-traitement sont des étapes intégrées. Le prétraitement est toujours la première étape et le posttraitement est toujours la dernière. Par défaut, il existe une scène nommée Par défaut. </p> <p> <b>Pour ajouter une nouvelle étape de traitement</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71">Dans le <span class="filepath"> Log Processing.cfg </span> fenêtre, clic droit <span class="uicontrol"> Phases </span> et cliquez sur <span class="uicontrol"> Ajouter </span> &gt; <span class="uicontrol"> Évaluation </span>. </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">Saisissez le nom de la nouvelle étape. </li> 
      </ul> </p> <p> <b>Pour supprimer une étape de traitement existante</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">Cliquez avec le bouton droit de la souris sur le nombre correspondant à l’étape que vous souhaitez supprimer, puis cliquez sur <span class="uicontrol"> Supprimer </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>Remarque : Lorsque vous spécifiez une <span class="wintitle"> Évaluation </span> dans <span class="wintitle"> Inclure le jeu de données de traitement du journal </span> , le nom de l’étape doit correspondre exactement au nom que vous saisissez ici. Voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Fichiers d’inclusion de jeux de données </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Heure de début </td> 
      <td colname="col2"> <p>Facultatif. Filtrez les données pour inclure les entrées du journal avec horodatages à cette heure ou après cette heure. Adobe recommande d’utiliser l’un des formats suivants pour l’heure : </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> 1er janvier 2013 HH:MM:SS EDT </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> 1er janvier 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Par exemple, en spécifiant "29 juillet 2013 00:00:00 EDT" comme l’heure de début inclut les données à partir du 29 juillet 2013, à 12:00:00H00 HNE. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtres de données </a>. </p> <p> Vous devez spécifier un fuseau horaire. Le fuseau horaire n’est pas défini par défaut sur GMT s’il n’est pas spécifié. Pour obtenir la liste des abréviations de fuseaux horaires prises en charge par le serveur Data Workbench, voir <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codes du fuseau horaire </a>. </p> <p> <p>Remarque : Le paramètre Utiliser les heures de début et de fin pour <span class="wintitle"> Sensor </span>, le fichier journal et les sources XML sont associés à ce paramètre. Voir les sections de <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Sources de journalisation </a> qui abordent ces types de sources. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fuseau horaire </td> 
      <td colname="col2"> <p>Facultatif. Fuseau horaire du serveur Data Workbench utilisé pour les conversions temporelles (comme la conversion représentée par le champ x-local-timestring ) pendant le traitement du journal. </p> <p> <p>Remarque : Vous devez spécifier le Fuseau horaire si vous souhaitez accéder au champ de l’heure convertie pendant la phase de traitement du journal de la construction du jeu de données. Dans le cas contraire, le serveur Data Workbench enregistre une erreur dans les journaux d’événements. </p> </p> <p>Voir <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fuseaux horaires </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformations </td> 
      <td colname="col2"> Facultatif. Adobe recommande de définir des transformations pour le traitement des journaux dans un ou plusieurs <span class="wintitle"> Inclure le jeu de données de traitement du journal </span> fichiers . Voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Fichiers d’inclusion de jeux de données de traitement journaux </a>. </td> 
   </tr> 
   </tbody> 
   </table>

1. Clic droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
1. Dans le [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche pour [!DNL Log Processing.cfg]dans le [!DNL User] , puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>* pour que les modifications apportées localement prennent effet. Le retraitement des données commence après la synchronisation du profil du jeu de données.

   >[!NOTE]
   >
   >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont écrasées lorsque vous installez des mises à jour sur ces profils.

   Pour plus d’informations sur le retraitement de vos données, voir [Retraitement et retransformation](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
