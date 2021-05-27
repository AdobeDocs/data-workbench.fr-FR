---
description: Vous pouvez créer un segment des éléments de n’importe quelle dimension dénombrable, puis générer les données de ce segment par lot ou en temps réel dans un fichier délimité par des tabulations.
title: Configurer des segments à exporter
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
exl-id: 4f53e02c-3f00-44b3-9f6d-a2f23903b3fa
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 6%

---

# Configurer des segments à exporter{#configure-segments-for-export}

Vous pouvez créer un segment des éléments de n’importe quelle dimension dénombrable, puis générer les données de ce segment par lot ou en temps réel dans un fichier délimité par des tabulations.

Chaque fois que vous exportez un segment, vous générez des données de mesure ou de dimension pour tous les éléments de dimension qui y sont inclus. Vous pouvez contrôler le formatage des données générées, de telle sorte que d’autres systèmes puissent facilement les charger.

>[!NOTE]
>
>Vous ne pouvez pas exporter de dimensions de rapport, car elles utilisent un fichier [!DNL report time.metric] à titre de référence. Pour pallier ce problème, si vous placez une balise [!DNL report time.metric] codée en dur dans le profil, l’exportation de segments peut l’utiliser comme point de référence pour les dimensions de rapport. Cependant, la balise [!DNL report time.metric] ne se met pas automatiquement à jour en fonction de l’heure du profil. Par conséquent, lorsque vous souhaitez modifier la référence de dimension de rapport, vous devez modifier le fichier [!DNL report time.metric] codé en dur.

Pour configurer un segment à exporter, vous devez ouvrir et modifier un fichier [!DNL .export].

1. Dans la balise [!DNL Profile Manager], cliquez sur le répertoire **[!UICONTROL Export]** de la colonne [!DNL File] pour en afficher le contenu.

       Si le répertoire d&#39;export n&#39;existe pas, créez-le comme suit :
   
   1. Accédez au répertoire d’installation de votre Data Workbench.
   1. Ouvrez le répertoire du profil avec lequel vous travaillez.
   1. Dans le répertoire Profile, créez un nouveau répertoire nommé &quot;Export&quot;.

1. Dans la balise [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la cellule vide de la colonne [!DNL User] du répertoire d&#39;export, puis cliquez sur **[!UICONTROL Create]** > **[!UICONTROL New Segment Export]**.

   Un fichier nommé [!DNL New Segment Export.export] apparaît dans la colonne [!DNL File] pour l’exportation.

1. Renommez le nouveau fichier en cliquant avec le bouton droit de la souris dans la colonne [!DNL User] du fichier et en saisissant le nouveau nom dans le paramètre Fichier .
1. Ouvrez le nouveau fichier en cliquant avec le bouton droit de la souris dans la colonne [!DNL User] correspondant au fichier et en cliquant sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   La fenêtre de configuration du fichier [!DNL .export] s’affiche.

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
   <td colname="col2"> <p>Facultatif. Programme à exécuter après la création du fichier de sortie. Ce champ doit faire référence à un fichier exécutable (fichier <span class="filepath"> .exe </span>) et non à une commande shell. </p> <p>Remarque :  L’exportation de segments échoue si le paramètre de commande contient un espace. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtre </td> 
   <td colname="col2"> <p>Facultatif. Un filtre nommé ou une expression de filtre. Vous pouvez créer un filtre nommé à l’aide d’un éditeur de filtres, puis saisir le nom de ce filtre ici ou saisir une expression de filtre. </p> <p>Pour plus d’informations sur les éditeurs de filtre, voir <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> Éditeurs de filtre </a>. Pour plus d’informations sur la syntaxe des expressions de filtre, voir <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Syntaxe des expressions de filtre </a>. </p> <p>Les éléments de niveau correspondant au filtre sont exportés, contrairement à tous les autres éléments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Niveau </td> 
   <td colname="col2"> <p>Dimension dénombrable dont les éléments doivent être exportés. </p> <p>Exemple : Un niveau Visiteur exporte une ligne de données pour chaque visiteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fichier de sortie </td> 
   <td colname="col2"> <p>Chemin et nom de fichier des données exportées. Si le profil s’exécute sur une grappe de serveurs de Data Workbench, chaque serveur de Data Workbench écrit un fichier de sortie contenant une partie des données. </p> <p>Le répertoire d’installation du serveur Data Workbench contient un répertoire Exports dans lequel vous pouvez enregistrer le fichier de sortie. Par exemple, vous pouvez saisir <span class="filepath"> Exports\Visitor Segment.txt </span>, où <span class="filepath"> Visitor Segment.txt </span> est le nom du fichier contenant les données exportées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Format de sortie </td> 
   <td colname="col2"> Données de mesure ou de dimension à exporter pour chaque élément Niveau. Si la sortie est un fichier délimité par des tabulations, les champs doivent être séparés par des caractères de tabulation et le format doit se terminer par les caractères de nouvelle ligne appropriés. Pour plus d’informations, voir <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> À propos du format de sortie </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de fin de planification </td> 
   <td colname="col2"> <p>Facultatif. Date et heure de fin du planning, y compris le fuseau horaire. </p> <p>Format : AAAA-MM-JJ hh:mm fuseau horaire </p> <p>Exemple : 2013-08-01 12:01 EDT </p> <p>Les exportations planifiées s’arrêtent alors ; toutefois, le fichier de sortie est toujours regénéré chaque fois que sa définition est modifiée. Ce champ n’a aucun sens sans définir le Planning de chaque. Pour plus d’informations sur les paramètres de fuseau horaire, consultez le <i>Guide de configuration des jeux de données</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Planifier chaque </td> 
   <td colname="col2"> Facultatif. Fréquence à laquelle générer à nouveau le fichier de sortie. Les valeurs prises en charge sont heure, jour, semaine et mois. Le fichier de sortie est toujours regénéré chaque fois que sa définition est modifiée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de début de la planification </td> 
   <td colname="col2"> <p>Facultatif. Date et heure de début du planning, notamment le fuseau horaire. </p> <p>Format : AAAA-MM-JJ hh:mm fuseau horaire </p> <p>Exemple : 2013-08-01 12:01 EDT </p> <p>Les exports planifiés démarrent à ce moment-là et le planning est relatif à cette heure. Ce champ n’a aucun sens sans définir <span class="wintitle"> Planification de chaque </span>. Pour plus d’informations sur les paramètres de fuseau horaire, consultez le <i>Guide de configuration des jeux de données</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite de temps (s) </td> 
   <td colname="col2"> Facultatif. Durée maximale autorisée pour s’écouler pendant la génération d’un export de segment. Si l’intervalle spécifié est dépassé, l’exportation recommence. La définition de cette valeur sur 0 (zéro) supprime la limite. La valeur par défaut est de 600 secondes. </td> 
  </tr> 
 </tbody> 
</table>

1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL (New)]** en haut de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
1. Pour mettre ce fichier à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche correspondant au fichier [!DNL .export] créé dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** *&lt;**[!UICONTROL working profile name]***.

   >[!NOTE]
   >
   >L’enregistrement du fichier [!DNL .export] sur le serveur du Data Workbench entraîne l’exécution immédiate de l’exportation une fois, même si l’heure de début de planification est définie sur une date et une heure futures.

   Voici un exemple de fichier [!DNL .export].

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >Le fichier [!DNL Visitor Segment.export] illustré dans l’exemple fait référence au filtre Segment du visiteur. La modification de la définition de ce filtre modifie la définition de l&#39;export.
