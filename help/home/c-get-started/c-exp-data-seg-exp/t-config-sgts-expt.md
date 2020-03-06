---
description: Vous pouvez créer un segment des éléments de n’importe quelle dimension dénombrable, puis générer des données pour ce segment par lot ou en temps réel dans un fichier délimité par des tabulations.
solution: Analytics
title: Configuration des segments à exporter
topic: Data workbench
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration des segments à exporter{#configure-segments-for-export}

Vous pouvez créer un segment des éléments de n’importe quelle dimension dénombrable, puis générer des données pour ce segment par lot ou en temps réel dans un fichier délimité par des tabulations.

Chaque fois que vous exportez un segment, vous générez des données de mesure ou de dimension pour tous les éléments de dimension qui y sont inclus. Vous pouvez contrôler le formatage des données générées, de telle sorte que d’autres systèmes puissent facilement les charger.

>[!NOTE]
>
>Vous ne pouvez pas exporter les dimensions de création de rapports, car elles utilisent un [!DNL report time.metric] fichier à titre de référence. Pour pallier ce problème, si vous placez un code [!DNL report time.metric] en dur dans le profil, l’exportation de segments peut l’utiliser comme point de référence pour les dimensions de création de rapports. Toutefois, la mise à jour [!DNL report time.metric] n’est pas automatique en fonction du profil A partir du moment. Par conséquent, lorsque vous souhaitez modifier la référence de dimension de création de rapports, vous devez modifier le [!DNL report time.metric] fichier codé en dur.

Pour configurer un segment à exporter, vous devez ouvrir et modifier un [!DNL .export] fichier.

1. Dans la [!DNL Profile Manager], cliquez sur le **[!UICONTROL Export]** répertoire dans la [!DNL File] colonne pour afficher son contenu.

       Si le répertoire d’exportation n’existe pas, créez-le comme suit :
   
   1. Accédez au répertoire d’installation des outils de données.
   1. Ouvrez le répertoire du profil avec lequel vous travaillez.
   1. Dans le répertoire Profile, créez un nouveau répertoire nommé &quot;Export&quot;.

1. Dans la [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la cellule vide dans la [!DNL User] colonne du répertoire d’exportation, puis cliquez sur **[!UICONTROL Create]** > **[!UICONTROL New Segment Export]**.

   Un fichier nommé [!DNL New Segment Export.export] apparaît dans la [!DNL File] colonne Exportation.

1. Renommez le nouveau fichier en cliquant avec le bouton droit de la souris dans la [!DNL User] colonne du fichier et en saisissant le nouveau nom dans le paramètre Fichier.
1. Ouvrez le nouveau fichier en cliquant avec le bouton droit dans la [!DNL User] colonne correspondant, puis en cliquant sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   La fenêtre de configuration du [!DNL .export] fichier apparaît.

1. Cliquez sur **[!UICONTROL Query]**, puis modifiez les champs du [!DNL .export] fichier comme décrit dans le tableau suivant :

<table id="table_C2EC8FCD3FA04DE78D2CADFA3F7FD8E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour ce paramètre... </th> 
   <th colname="col2" class="entry"> Fournissez ces informations... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Commande </td> 
   <td colname="col2"> <p>Facultatif. Programme à exécuter après la création du fichier de sortie. Ce champ doit faire référence à un exécutable (fichier .exe <span class="filepath"> </span> ), et non à une commande shell. </p> <p>Remarque :  L’exportation du segment échoue s’il existe un espace dans le paramètre de commande. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtrer </td> 
   <td colname="col2"> <p>Facultatif. Filtre nommé ou expression de filtre. Vous pouvez soit créer un filtre nommé à l’aide d’un éditeur de filtre, puis taper le nom de ce filtre ici, soit taper une expression de filtre elle-même. </p> <p>Pour plus d’informations sur les éditeurs de filtres, voir <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> Filtrer les éditeurs </a>. Pour plus d’informations sur la syntaxe des expressions de filtre, voir <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Syntaxe pour les expressions de filtre </a>. </p> <p>Les éléments de niveau qui correspondent au filtre sont exportés, contrairement à tous les autres éléments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Niveau </td> 
   <td colname="col2"> <p>Dimension dénombrable dont les éléments doivent être exportés. </p> <p>Exemple : Un niveau Visiteur exporte une ligne de données pour chaque visiteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fichier de sortie </td> 
   <td colname="col2"> <p>Chemin d’accès et nom de fichier des données exportées. Si le profil est exécuté sur une grappe de serveurs Outils de données, chaque serveur écrit un fichier de sortie contenant une partie des données. </p> <p>Le répertoire d’installation du serveur Outils de données contient un répertoire Exports dans lequel vous pouvez enregistrer le fichier de sortie. Par exemple, vous pouvez entrer <span class="filepath"> Exportations\Segment du visiteur.txt </span>, où <span class="filepath"> Segment du visiteur.txt </span> est le nom du fichier contenant les données exportées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Format de sortie </td> 
   <td colname="col2"> Données de mesure ou de dimension à exporter pour chaque élément de niveau. Si la sortie est un fichier délimité par des tabulations, les champs doivent être séparés par des caractères de tabulation et le format doit se terminer par les caractères de nouvelle ligne appropriés. Pour plus d’informations, voir <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> A propos du format de sortie </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de fin de planification </td> 
   <td colname="col2"> <p>Facultatif. Date et heure de fin de la planification, y compris le fuseau horaire. </p> <p>Format : AAAA-MM-JJ hh:mm fuseau horaire </p> <p>Exemple : 2013-08-01 12:01 HAE </p> <p>Les exportations planifiées s'arrêtent à ce moment-là; toutefois, le fichier de sortie est toujours régénéré chaque fois que sa définition est modifiée. Ce champ n’a aucun sens sans définir le paramètre Planifier chaque. Pour plus d’informations sur les paramètres de fuseau horaire, voir le Guide <i>de configuration des jeux de</i>données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Planifier chaque </td> 
   <td colname="col2"> Facultatif. Fréquence à laquelle le fichier de sortie doit être régénéré. Les valeurs prises en charge sont heure, jour, semaine et mois. Le fichier de sortie est toujours régénéré chaque fois que sa définition est modifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de début de planification </td> 
   <td colname="col2"> <p>Facultatif. Date et heure de début de la planification, y compris le fuseau horaire. </p> <p>Format : AAAA-MM-JJ hh:mm fuseau horaire </p> <p>Exemple : 2013-08-01 12:01 HAE </p> <p>Les exportations planifiées démarrent à ce moment et le calendrier est relatif à ce moment. Ce champ n'a aucun sens sans définir <span class="wintitle"> Planifier tous les </span>. Pour plus d’informations sur les paramètres de fuseau horaire, voir le Guide <i>de configuration des jeux de</i>données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite de temps (s) </td> 
   <td colname="col2"> Facultatif. durée maximale autorisée pour s’écouler pendant la génération d’une exportation de segment. Si l’intervalle spécifié est dépassé, l’exportation recommence. La définition de cette valeur sur 0 (zéro) supprime la limite. La valeur par défaut est de 600 secondes. </td> 
  </tr> 
 </tbody> 
</table>

1. Cliquez avec le bouton droit **[!UICONTROL (New)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
1. Pour rendre ce fichier accessible à tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche du [!DNL .export] fichier créé dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >L’enregistrement du [!DNL .export] fichier sur le serveur Outils de données entraîne l’exécution immédiate de l’exportation, même si l’heure de début de planification est définie sur une date et une heure futures.

   The following is a sample [!DNL .export] file.

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >Le [!DNL Visitor Segment.export] fichier illustré dans l’exemple fait référence au filtre Segment de visiteur. La modification de la définition de ce filtre modifie la définition de l’exportation.

