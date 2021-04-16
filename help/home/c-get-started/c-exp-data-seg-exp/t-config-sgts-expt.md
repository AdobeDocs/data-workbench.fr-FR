---
description: Vous pouvez créer un segment des éléments de n’importe quelle dimension dénombrable, puis générer des données pour ce segment par lot ou en temps réel dans un fichier délimité par des tabulations.
title: Configurer des segments à exporter
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
exl-id: 4f53e02c-3f00-44b3-9f6d-a2f23903b3fa
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 6%

---

# Configurer des segments à exporter{#configure-segments-for-export}

Vous pouvez créer un segment des éléments de n’importe quelle dimension dénombrable, puis générer des données pour ce segment par lot ou en temps réel dans un fichier délimité par des tabulations.

Chaque fois que vous exportez un segment, vous générez des données de mesure ou de dimension pour tous les éléments de dimension qui y sont inclus. Vous pouvez contrôler le formatage des données générées, de telle sorte que d’autres systèmes puissent facilement les charger.

>[!NOTE]
>
>Vous ne pouvez pas exporter les dimensions de rapports, car elles utilisent un fichier [!DNL report time.metric] pour référence. Pour pallier ce problème, si vous placez un [!DNL report time.metric] codé en dur dans le profil, l’exportation de segments peut l’utiliser comme point de référence pour les dimensions du rapports. Cependant, [!DNL report time.metric] ne se met pas automatiquement à jour en fonction du profil A partir du moment. Par conséquent, si vous souhaitez modifier la référence de dimension de rapports, vous devez modifier le fichier codé en dur [!DNL report time.metric].

Pour configurer un segment à exporter, vous devez ouvrir et modifier un fichier [!DNL .export].

1. Dans la colonne [!DNL Profile Manager], cliquez sur le répertoire **[!UICONTROL Export]** de la colonne [!DNL File] pour en afficher le contenu.

       Si le répertoire d’exportation n’existe pas, créez-le comme suit :
   
   1. Accédez au répertoire d’installation du Data Workbench.
   1. Ouvrez le répertoire du profil avec lequel vous travaillez.
   1. Dans le répertoire du Profil, créez un nouveau répertoire nommé &quot;Exporter&quot;.

1. Dans [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la cellule vide de la colonne [!DNL User] du répertoire d’exportation, puis cliquez sur **[!UICONTROL Create]** > **[!UICONTROL New Segment Export]**.

   Un fichier nommé [!DNL New Segment Export.export] apparaît dans la colonne [!DNL File] pour l&#39;exportation.

1. Renommez le nouveau fichier en cliquant avec le bouton droit de la souris dans la colonne [!DNL User] du fichier et en saisissant le nouveau nom dans le paramètre Fichier.
1. Ouvrez le nouveau fichier en cliquant avec le bouton droit de la souris dans la colonne [!DNL User] du fichier et en cliquant sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   La fenêtre de configuration du fichier [!DNL .export] s&#39;affiche.

1. Cliquez sur **[!UICONTROL Query]**, puis modifiez les champs du fichier [!DNL .export] comme décrit dans le tableau suivant :

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
   <td colname="col2"> <p>Facultatif. Programme à exécuter après la création du fichier de sortie. Ce champ doit référencer un exécutable (un fichier <span class="filepath"> .exe </span>), et non une commande shell. </p> <p>Remarque :  L’exportation du segment échoue s’il existe un espace dans le paramètre de commande. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtre </td> 
   <td colname="col2"> <p>Facultatif. Un filtre nommé ou une expression de filtre. Vous pouvez soit créer un filtre nommé à l’aide d’un éditeur de filtres, puis taper le nom de ce filtre ici, soit taper une expression de filtre elle-même. </p> <p>Pour plus d'informations sur les éditeurs de filtres, voir <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> Éditeurs de filtres </a>. Pour plus d'informations sur la syntaxe des expressions de filtre, voir <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Syntaxe pour les Expressions de filtre </a>. </p> <p>Les éléments de niveau correspondant au filtre sont exportés, contrairement à tous les autres éléments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Niveau </td> 
   <td colname="col2"> <p>Dimension dénombrable dont les éléments doivent être exportés. </p> <p>Exemple : Un niveau de Visiteur exporte une ligne de données pour chaque visiteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fichier de sortie </td> 
   <td colname="col2"> <p>Chemin d’accès et nom de fichier des données exportées. Si le profil s’exécute sur une grappe de serveurs Data Workbench, chaque serveur Data Workbench écrit un fichier de sortie contenant une partie des données. </p> <p>Le répertoire d’installation du serveur Data Workbench contient un répertoire Exports dans lequel vous pouvez enregistrer le fichier de sortie. Par exemple, vous pouvez entrer <span class="filepath"> Exports\Visiteur Segment.txt </span>, où <span class="filepath"> Visiteur Segment.txt </span> est le nom du fichier contenant les données exportées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Format de sortie </td> 
   <td colname="col2"> Données de mesure ou de dimension à exporter pour chaque élément de niveau. Si la sortie est un fichier délimité par des tabulations, les champs doivent être séparés par des caractères de tabulation et le format doit se terminer par les caractères de nouvelle ligne appropriés. Pour plus d’informations, voir <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> A propos du format de sortie </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de fin de planification </td> 
   <td colname="col2"> <p>Facultatif. Date et heure de fin de la planification, y compris le fuseau horaire. </p> <p>Format : AAAA-MM-JJ hh:mm fuseau horaire </p> <p>Exemple : 2013-08-01 12:01 HAE </p> <p>Les exportations planifiées s'arrêtent alors ; toutefois, le fichier de sortie est toujours régénéré chaque fois que sa définition est modifiée. Ce champ n'a pas de sens sans définir le calendrier Tous. Pour plus d'informations sur les paramètres de fuseau horaire, consultez le <i>Guide de configuration des ensembles de données</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Planifier chaque </td> 
   <td colname="col2"> Facultatif. Fréquence à laquelle le fichier de sortie doit être régénéré. Les valeurs prises en charge sont heure, jour, semaine et mois. Le fichier de sortie est toujours régénéré chaque fois que sa définition est modifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de Début de planification </td> 
   <td colname="col2"> <p>Facultatif. Date et heure de début de la planification, y compris le fuseau horaire. </p> <p>Format : AAAA-MM-JJ hh:mm fuseau horaire </p> <p>Exemple : 2013-08-01 12:01 HAE </p> <p>Début des exportations planifiées pour l’instant et le calendrier est relatif à cette date. Ce champ n'a pas de sens sans définir <span class="wintitle"> Planification de </span>. Pour plus d'informations sur les paramètres de fuseau horaire, consultez le <i>Guide de configuration des ensembles de données</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite de temps (s) </td> 
   <td colname="col2"> Facultatif. Durée maximale autorisée pour s’écouler pendant la génération d’une exportation de segment. Si l’intervalle spécifié est dépassé, l’exportation est répartie sur les débuts. La définition de cette valeur sur 0 (zéro) supprime la limite. La valeur par défaut est de 600 secondes. </td> 
  </tr> 
 </tbody> 
</table>

1. Cliquez avec le bouton droit **[!UICONTROL (New)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
1. Pour mettre ce fichier à la disposition de tous les utilisateurs du profil de travail, cochez la case correspondant au fichier [!DNL .export] créé dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.

   >[!NOTE]
   >
   >L&#39;enregistrement du fichier [!DNL .export] sur le serveur Data Workbench entraîne l&#39;exécution immédiate de l&#39;exportation, même si l&#39;heure de Début planifiée est définie sur une date et une heure futures.

   Voici un exemple de fichier [!DNL .export].

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >Le fichier [!DNL Visitor Segment.export] illustré dans l&#39;exemple fait référence au filtre de segment de Visiteur. La modification de la définition de ce filtre modifie la définition de l’exportation.
