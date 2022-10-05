---
description: Vous pouvez créer un segment des éléments de n’importe quelle dimension dénombrable, puis générer les données de ce segment par lot ou en temps réel dans un fichier délimité par des tabulations.
title: Configurer des segments à exporter
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
exl-id: 4f53e02c-3f00-44b3-9f6d-a2f23903b3fa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 6%

---

# Configurer des segments à exporter{#configure-segments-for-export}

{{eol}}

Vous pouvez créer un segment des éléments de n’importe quelle dimension dénombrable, puis générer les données de ce segment par lot ou en temps réel dans un fichier délimité par des tabulations.

Chaque fois que vous exportez un segment, vous générez des données de mesure ou de dimension pour tous les éléments de dimension qui y sont inclus. Vous pouvez contrôler le formatage des données générées, de telle sorte que d’autres systèmes puissent facilement les charger.

>[!NOTE]
>
>Vous ne pouvez pas exporter de dimensions de rapport, car elles utilisent une [!DNL report time.metric] à titre de référence. Pour pallier ce problème, placez un code en dur. [!DNL report time.metric] dans le profil, l’exportation de segments peut l’utiliser comme point de référence pour les dimensions de création de rapports. Toutefois, la variable [!DNL report time.metric] ne se met pas automatiquement à jour en fonction de l’heure du profil. Par conséquent, si vous souhaitez modifier la référence de dimension de rapport, vous devez modifier le code en dur. [!DNL report time.metric] fichier .

Pour configurer un segment à exporter, vous devez ouvrir et modifier un [!DNL .export] fichier .

1. Dans le [!DNL Profile Manager], cliquez sur le bouton **[!UICONTROL Export]** dans le répertoire [!DNL File] pour afficher son contenu.

       Si le répertoire d&#39;export n&#39;existe pas, créez-le comme suit :
   
   1. Accédez au répertoire d’installation de votre Data Workbench.
   1. Ouvrez le répertoire du profil avec lequel vous travaillez.
   1. Dans le répertoire Profile, créez un nouveau répertoire nommé &quot;Export&quot;.

1. Dans le [!DNL Profile Manager], cliquez avec le bouton droit sur la cellule vide dans la variable [!DNL User] pour le répertoire d’exportation, puis cliquez sur **[!UICONTROL Create]** > **[!UICONTROL New Segment Export]**.

   Un fichier nommé [!DNL New Segment Export.export] apparaît dans la variable [!DNL File] pour l’exportation.

1. Renommez le nouveau fichier en cliquant avec le bouton droit dans la [!DNL User] pour le fichier et en saisissant le nouveau nom dans le paramètre File .
1. Ouvrez le nouveau fichier en cliquant avec le bouton droit de la souris dans le [!DNL User] pour le fichier et en cliquant sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   La fenêtre de configuration de la [!DNL .export] s’affiche.

1. Cliquez sur **[!UICONTROL Query]**, puis modifiez les champs du [!DNL .export] comme décrit dans le tableau suivant :

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
   <td colname="col2"> <p>Facultatif. Programme à exécuter après la création du fichier de sortie. Ce champ doit faire référence à un fichier exécutable (un <span class="filepath"> .exe </span> ), et non une commande shell. </p> <p>Remarque : L’exportation de segments échoue si le paramètre de commande contient un espace. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtre </td> 
   <td colname="col2"> <p>Facultatif. Un filtre nommé ou une expression de filtre. Vous pouvez créer un filtre nommé à l’aide d’un éditeur de filtres, puis saisir le nom de ce filtre ici ou saisir une expression de filtre. </p> <p>Pour plus d’informations sur les éditeurs de filtre, voir <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> Éditeurs de filtre </a>. Pour plus d’informations sur la syntaxe de l’expression de filtre, voir <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Syntaxe des expressions de filtre </a>. </p> <p>Les éléments de niveau correspondant au filtre sont exportés, contrairement à tous les autres éléments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Niveau </td> 
   <td colname="col2"> <p>Dimension dénombrable dont les éléments doivent être exportés. </p> <p>Exemple : Un niveau Visiteur exporte une ligne de données pour chaque visiteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fichier de sortie </td> 
   <td colname="col2"> <p>Chemin et nom de fichier des données exportées. Si le profil s’exécute sur une grappe de serveurs de Data Workbench, chaque serveur de Data Workbench écrit un fichier de sortie contenant une partie des données. </p> <p>Le répertoire d’installation du serveur Data Workbench contient un répertoire Exports dans lequel vous pouvez enregistrer le fichier de sortie. Par exemple, vous pouvez saisir <span class="filepath"> Exports\Visitor Segment.txt </span>où <span class="filepath"> Visitor Segment.txt </span> est le nom du fichier contenant les données exportées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Format de sortie </td> 
   <td colname="col2"> Données de mesure ou de dimension à exporter pour chaque élément Niveau. Si la sortie est un fichier délimité par des tabulations, les champs doivent être séparés par des caractères de tabulation et le format doit se terminer par les caractères de nouvelle ligne appropriés. Pour plus d’informations, voir <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> A propos du format de sortie </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de fin de planification </td> 
   <td colname="col2"> <p>Facultatif. Date et heure de fin du planning, y compris le fuseau horaire. </p> <p>Format : AAAA-MM-JJ hh:mm fuseau horaire </p> <p>Exemple : 2013-08-01 12:01 EDT </p> <p>Les exportations planifiées s’arrêtent alors ; toutefois, le fichier de sortie est toujours regénéré chaque fois que sa définition est modifiée. Ce champ n’a aucun sens sans définir le Planning de chaque. Pour plus d’informations sur les paramètres de fuseau horaire, voir <i>Guide de configuration des jeux de données</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Planifier chaque </td> 
   <td colname="col2"> Facultatif. Fréquence à laquelle générer à nouveau le fichier de sortie. Les valeurs prises en charge sont heure, jour, semaine et mois. Le fichier de sortie est toujours regénéré chaque fois que sa définition est modifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de début de la planification </td> 
   <td colname="col2"> <p>Facultatif. Date et heure de début du planning, notamment le fuseau horaire. </p> <p>Format : AAAA-MM-JJ hh:mm fuseau horaire </p> <p>Exemple : 2013-08-01 12:01 EDT </p> <p>Les exports planifiés démarrent à ce moment-là et le planning est relatif à cette heure. Ce champ n'a aucun sens sans définir <span class="wintitle"> Planifier chaque </span>. Pour plus d’informations sur les paramètres de fuseau horaire, voir <i>Guide de configuration des jeux de données</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite de temps (s) </td> 
   <td colname="col2"> Facultatif. Durée maximale autorisée pour s’écouler pendant la génération d’un export de segment. Si l’intervalle spécifié est dépassé, l’exportation recommence. La définition de cette valeur sur 0 (zéro) supprime la limite. La valeur par défaut est de 600 secondes. </td> 
  </tr> 
 </tbody> 
</table>

1. Clic droit **[!UICONTROL (New)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
1. Pour mettre ce fichier à disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche correspondant au [!DNL .export] dans le fichier [!DNL User] , puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >Enregistrement de la variable [!DNL .export] sur le serveur de Data Workbench, l’exportation s’exécute immédiatement, même si l’heure de début de planification est définie sur une date et une heure ultérieures.

   Voici un exemple : [!DNL .export] fichier .

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >Le [!DNL Visitor Segment.export] s’affiche dans l’exemple et fait référence au filtre Segment du visiteur. La modification de la définition de ce filtre modifie la définition de l&#39;export.
