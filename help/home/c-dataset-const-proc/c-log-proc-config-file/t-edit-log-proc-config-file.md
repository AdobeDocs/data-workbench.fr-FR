---
description: Procédure de modification du fichier Log Processing.cfg pour un profil de jeux de données.
title: Modification du fichier de configuration de traitement du journal
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
exl-id: 294063ef-6771-4310-8198-df57fab1e2b4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 2%

---

# Modification du fichier de configuration de traitement du journal{#editing-the-log-processing-configuration-file}

Procédure de modification du fichier Log Processing.cfg pour un profil de jeux de données.

1. Lorsque vous travaillez dans votre profil de jeux de données, ouvrez [!DNL Profile Manager] et cliquez sur **[!UICONTROL Dataset]** pour en afficher le contenu.

   Pour plus d&#39;informations sur l&#39;ouverture et l&#39;utilisation de [!DNL Profile Manager], consultez le *Guide de l&#39;utilisateur Data Workbench*.

   >[!NOTE]
   >
   >Un sous-répertoire de traitement du journal peut exister dans le répertoire des jeux de données. Ce sous-répertoire contient les fichiers [!DNL Log Processing Dataset Include] créés pour un ou plusieurs profils hérités. Voir [Jeu de données Inclure les fichiers](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Cliquez avec le bouton droit de la souris sur la coche en regard de [!DNL Log Processing.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. La fenêtre [!DNL Log Processing.cfg] s&#39;affiche.

   Vous pouvez également ouvrir le fichier [!DNL Log Processing.cfg] à partir d&#39;un [!DNL Transformation Dependency Map]. Pour plus d&#39;informations sur les mappages des dépendances de transformation, voir [Outils de configuration des jeux de données](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. Modifiez les paramètres du fichier de configuration à l’aide du tableau suivant comme guide.

   Lors de la modification du fichier [!DNL Log Processing.cfg] dans une fenêtre de l&#39;outil de données, vous pouvez utiliser des touches de raccourci pour les fonctions de modification de base, notamment couper ( Ctrl+x ), copier ( Ctrl+c), coller ( Ctrl+v ), annuler ( Ctrl+z ), rétablir ( Ctrl+Maj+z ), sélectionner une section (cliquer+faire glisser) et sélectionner tout ( Ctrl+a ). Vous pouvez également utiliser les raccourcis pour copier et coller le texte d&#39;un fichier de configuration ( [!DNL .cfg]) vers un autre.

   >[!NOTE]
   >
   >Un fichier [!DNL Log Processing Dataset Include] pour un profil hérité contient un sous-ensemble des paramètres décrits dans le tableau suivant ainsi que quelques autres paramètres supplémentaires. Voir [Jeu de données Inclure les fichiers](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

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
      <td colname="col2"> Sources de données. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Sources de journal </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Heure de fin </td> 
      <td colname="col2"> <p>Facultatif. Filtrez les données pour inclure les entrées de journal avec horodatages jusqu’à cette heure, mais pas cette heure. L’Adobe recommande d’utiliser l’un des formats suivants pour l’heure : </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">1er janvier 2013 HH:MM:SS EDT </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">1er janvier 2013 HH:MM:SS GMT </li> 
      </ul> <p>Par exemple, la spécification du 29 juillet 2013 à 00:00:00 EDT comme heure de fin inclut les données jusqu’au 28 juillet 2013 à 11h59:59 EDT. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtres de données </a>. </p> <p>Vous devez spécifier un fuseau horaire. Le fuseau horaire n’est pas défini par défaut sur GMT s’il n’est pas spécifié. Pour obtenir la liste des abréviations de fuseau horaire prises en charge par le serveur de l’outil de données, voir <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codes de fuseau horaire </a>. </p> <p> <p>Remarque :  Le paramètre Use Début/End Times parameter for <span class="wintitle"> Sensor </span>, log file et sources XML est associé à ce paramètre. Consultez les sections <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Sources de journal </a> qui traitent de ces types de source. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Champs </td> 
      <td colname="col2"> Facultatif. Adobe recommande de définir <span class="wintitle"> Champs </span> dans un ou plusieurs <span class="wintitle"> Jeu de données de traitement du journal Inclure </span> fichiers. Voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Jeu de données de traitement du journal Inclure les fichiers </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nombre maximal d'octets clés du groupe </td> 
      <td colname="col2"> <p>Quantité maximale de données de événement que le serveur peut traiter pour un seul ID de suivi. Les données dépassant cette limite sont filtrées à partir du processus de construction des ensembles de données. Cette valeur doit être définie sur 2e6 lorsque le fractionnement des clés est principal et 1e6 lorsque le fractionnement des clés n’est pas principal. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Division de clés </a>. </p> <p> <p>Remarque :  Ne modifiez pas cette valeur sans consulter l’Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Seuil de hachage </td> 
      <td colname="col2"> <p>Facultatif. Facteur d'échantillonnage pour le sous-échantillonnage aléatoire des rangées. Si la valeur est définie sur n, un seul identifiant de suivi sur n entre dans le jeu de données, réduisant le nombre total de lignes dans le jeu de données par un facteur n. </p> <p>Pour créer un jeu de données qui requiert une précision de 100 % (c'est-à-dire, pour inclure toutes les lignes), vous devez définir le seuil de hachage sur 1. </p> <p>Valeurs: </p> <span class="filepath"> Seuil de hachage = 1  </span> (100 % des données, y compris toutes les lignes). <p> <span class="filepath"> Seuil de hachage = 2  </span> (1/2 des données et comprend la moitié des lignes). </p> <p> <span class="filepath"> Seuil de hachage = 3  </span>(1/3 des données et comprend une des trois lignes, mais arrondit à 34 % la fin de la Requête) </p> <p> <span class="filepath"> Seuil de hachage = 4  </span>(1/4 des données et comprend une ligne sur quatre). </p> <p> </p> <p> <p>Remarque :  L'utilisation d'un seuil de hachage <span class="filepath"> = 8 </span> fournit 1/8ème des données, soit 12,5 %. Cependant, la valeur <span class="uicontrol"> Requête terminée </span> est arrondie à 13 % pour cette valeur. Les autres exemples incluent un <span class="filepath"> seuil de hachage = 6 </span> qui résulte en une résolution de requête de 17 %. Un <span class="filepath"> seuil de hachage = 13 </span>produit une résolution de requête de 8 %. </p> </p> <p>Si <span class="wintitle"> Seuil de hachage </span> est spécifié dans les fichiers <span class="filepath"> Log Processing.cfg </span> et <span class="filepath"> Transformation.cfg </span>, il n'est pas appliqué dans l'ordre ; la valeur maximale définie dans l'un des fichiers de configuration s'applique. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtres de données </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condition d’entrée du journal </td> 
      <td colname="col2"> Facultatif. Définit les règles selon lesquelles les entrées du journal sont prises en compte pour l’inclusion dans le jeu de données. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condition d'entrée de journal </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Retraiter </td> 
      <td colname="col2"> <p>Facultatif. Tout caractère ou combinaison de caractères peut être saisi ici. La modification de ce paramètre et l’enregistrement du fichier sur l’ordinateur du serveur de l’outil de données initie le retraitement des données. </p> <p>Voir <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Retraitement et retransformation </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Split Key Bucket Space </td> 
      <td colname="col2"> <p>Paramètre impliqué dans le fractionnement des clés. Sa valeur doit être 6e6 lorsque le fractionnement des clés est principal. Voir <a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split"> Division de clés </a>. </p> <p> <p>Remarque :  Ne modifiez pas cette valeur sans consulter l’Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fractionner les octets clés </td> 
      <td colname="col2"> <p>Paramètre impliqué dans le fractionnement des clés. Sa valeur doit être 1e6 lorsque le fractionnement des clés est principal et 0 lorsque le fractionnement des clés n’est pas principal. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Division de clés </a>. </p> <p> <p>Remarque :  Ne modifiez pas cette valeur sans consulter l’Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Proportion d'espace de clé fractionnée </td> 
      <td colname="col2"> <p>Paramètre impliqué dans le fractionnement des clés. Sa valeur doit être 10 lorsque la division de clé est principale. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Division de clés </a>. </p> <p> <p>Remarque :  Ne modifiez pas cette valeur sans consulter l’Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Etapes </td> 
      <td colname="col2"> <p>Facultatif. Les noms des étapes de traitement pouvant être utilisées dans le jeu de données de traitement du journal <span class="wintitle"> incluent des fichiers </span>. Les étapes de traitement permettent d'organiser les transformations définies dans les fichiers <span class="wintitle"> Jeu de données de traitement du journal Inclure </span>. Ce paramètre est très utile si vous avez défini une ou plusieurs transformations dans plusieurs fichiers <span class="wintitle"> Jeu de données de traitement du journal Inclure </span> et que vous souhaitez que des transformations spécifiques soient effectuées à des moments spécifiques pendant le traitement du journal. </p> <p>L'ordre dans lequel vous listes les étapes ici détermine l'ordre dans lequel les transformations dans le jeu de données de traitement du journal <span class="wintitle"> Inclure </span> sont exécutées pendant le traitement du journal. Le prétraitement et le post-traitement sont des étapes intégrées. Le prétraitement est toujours la première étape et le post-traitement est toujours la dernière étape. Par défaut, il existe une étape nommée Par défaut. </p> <p> <b>Pour ajouter une nouvelle étape de traitement</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71">Dans la fenêtre <span class="filepath"> Log Processing.cfg </span>, cliquez avec le bouton droit de la souris sur <span class="uicontrol"> Etapes </span> et cliquez sur <span class="uicontrol"> Ajouter la nouvelle </span> étape <span class="uicontrol"> </span>. </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">Entrez le nom de la nouvelle étape. </li> 
      </ul> </p> <p> <b>Pour supprimer une étape de traitement existante</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">Cliquez avec le bouton droit de la souris sur le numéro correspondant à l’étape à supprimer, puis cliquez sur <span class="uicontrol"> Supprimer </span><i>&lt; <span class="uicontrol"> #stage_number </span></i>. </li> 
      </ul> </p> <p> <p>Remarque :  Lorsque vous spécifiez une étape <span class="wintitle"> </span> dans un jeu de données de traitement du journal Inclure </span> fichiers, le nom de l’étape doit correspondre exactement au nom que vous saisissez ici. <span class="wintitle"> Voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Jeu de données Inclure les fichiers </a>. </span></p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Heure de début </td> 
      <td colname="col2"> <p>Facultatif. Filtrez les données pour inclure les entrées de journal avec horodatage à cette heure ou après cette date. L’Adobe recommande d’utiliser l’un des formats suivants pour l’heure : </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> 1er janvier 2013 HH:MM:SS EDT </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> 1er janvier 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Par exemple, la spécification de "29 juillet 2013 à 00:00:00 EDT" comme heure du Début inclut des données commençant le 29 juillet 2013 à 12h00 EDT. Voir <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtres de données </a>. </p> <p> Vous devez spécifier un fuseau horaire. Le fuseau horaire n’est pas défini par défaut sur GMT s’il n’est pas spécifié. Pour obtenir la liste des abréviations de fuseau horaire prises en charge par le serveur de l’outil de données, voir <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codes de fuseau horaire </a>. </p> <p> <p>Remarque :  Le paramètre Use Début/End Times parameter for <span class="wintitle"> Sensor </span>, log file et sources XML est associé à ce paramètre. Consultez les sections <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Sources de journal </a> qui traitent de ces types de source. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fuseau horaire </td> 
      <td colname="col2"> <p>Facultatif. Fuseau horaire du serveur de l’outil de données utilisé pour les conversions temporelles (comme la conversion représentée par le champ x-local-timestring) pendant le traitement du journal. </p> <p> <p>Remarque :  Vous devez spécifier le fuseau horaire si vous souhaitez accéder au champ de temps converti pendant la phase de traitement du journal de la construction du jeu de données. Sinon, le serveur de l’outil de données enregistre une erreur dans les journaux de événement. </p> </p> <p>Voir <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fuseaux horaires </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformations </td> 
      <td colname="col2"> Facultatif. Adobe recommande de définir des transformations pour le traitement des journaux dans un ou plusieurs fichiers <span class="wintitle"> Jeu de données de traitement des journaux Inclure </span>. Voir <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> Jeu de données de traitement du journal Inclure les fichiers </a>. </td> 
   </tr> 
   </tbody> 
   </table>

1. Cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.
1. Dans la colonne [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL Log Processing.cfg]dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]*** pour que les modifications apportées localement prennent effet. Le retraitement des données commence après la synchronisation du profil du jeu de données.

   >[!NOTE]
   >
   >N&#39;enregistrez le fichier de configuration modifié dans aucun des profils internes fournis par Adobe, car vos modifications sont remplacées lorsque vous installez des mises à jour de ces profils.

   Pour plus d’informations sur le retraitement de vos données, voir [Retraitement et retransformation](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
