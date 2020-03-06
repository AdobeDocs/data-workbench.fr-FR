---
description: Ouvrez l’option Attribution adéquate dans le menu Premium et procédez comme suit pour créer un modèle d’attribution adaptée.
title: Créer un modèle d’attribution adapté
uuid: d1fd0340-1917-41bc-9a08-e78a79d084e7
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Créer un modèle d’attribution adapté{#build-a-best-fit-attribution-model}

Ouvrez l’option Attribution adéquate dans le menu Premium et procédez comme suit pour créer un modèle d’attribution adaptée.

Consultez un aperçu de l’attribution [adaptée](../../../../home/c-get-started/c-attribution-profiles/c-attrib-algorithmic/c-attrib-algorithmic.md#concept-237feb6e9c4d49efaf75399297dcb9d1).

1. Ouvrez **Optimisation**.

   Ouvrez un espace de travail et cliquez sur **[!UICONTROL Premium]** > **[!UICONTROL Best Fit Attribution]**.

   ![](assets/attrib_windows_launch.png)

   >[!NOTE]
   >
   >L’option Ajuster au mieux est une fonction d’Adobe Analytics Premium qui requiert que vous activiez Premium dans votre profil. Vous devez mettre à jour votre certificat et ajouter le profil Premium à votre fichier profile.cfg. Voir Mise à niveau [du serveur DWB : 6.2 à 6.3](https://docs.adobe.com/content/help/en/data-workbench/using/install/upgrade-dwb/c-6-2-to-6-3-upgrade.html) pour DWB 6.3.

1. Set the **[!UICONTROL Success]** metric.

   >[!NOTE]
   >
   >Vous pouvez faire glisser une mesure d’un **[!UICONTROL Finder]** tableau vers le volet gauche de la visualisation Attribution ou sélectionner une mesure dans le menu **Entrées** .

   Cliquez sur **[!UICONTROL Inputs]** > **[!UICONTROL Set Success]**. Le menu des mesures s’ouvre. ![](assets/attrib_set_success_metric.png)

   Sélectionnez une mesure qui identifie une conversion réussie.

1. (Facultatif) Définissez la mesure **Recettes** .

   Définissez une mesure pour évaluer les recettes dans le processus de conversion.

1. Définissez la mesure **tactile** .

   >[!NOTE]
   >
   >La définition d’une mesure tactile n’est requise que si vous tentez de créer automatiquement des mesures de réussite en faisant glisser des éléments de dimension sur la visualisation.

   Cliquez sur le **[!UICONTROL Inputs]** menu et sélectionnez **Définir la touche** ou faites glisser une mesure depuis le Finder. ![](assets/attrib_set_touch.png)

   Elle sera utilisée pour dériver des mesures de canal lorsque des éléments de dimension sont utilisés comme entrées.

1. Définissez une fenêtre **Réussite** .

   Cliquez sur [!DNL Inputs > Success Window]. Sélectionnez une plage de dates dans un tableau, puis nommez la fenêtre Succès. Cliquez sur **[!UICONTROL Workspace Selection]** et les dates sélectionnées seront attribuées comme période pour la mesure de réussite.

   ![](assets/attrib_set_success_window.png)

   >[!NOTE]
   >
   >Puisque la fenêtre Réussite est une sélection de poste de travail, vous pouvez inclure n’importe quelle(s) dimension(s) à votre fenêtre Réussite.

1. Définissez un **[!UICONTROL Touch Window]**.

   Cliquez sur [!DNL Inputs > Touch Window]. Sélectionnez une plage de dates dans un tableau, puis nommez la fenêtre tactile. Cliquez sur **[!UICONTROL Workspace Selection]** et les dates sélectionnées seront attribuées comme période pour la mesure de réussite.

   ![](assets/attrib_set_touch_window.png)

   Par défaut, la fenêtre **tactile** est définie sur la même période que la **[!UICONTROL Success]** fenêtre.

1. (Facultatif) Définissez un filtre de formation.

   Vous pouvez également spécifier un filtre **de** formation dans l’espace de travail pour filtrer les données des visiteurs.

   >[!NOTE]
   >
   >En définissant les fenêtres Réussite et Touche, vous pouvez appliquer le filtre Formation aux sélections actuelles de l’espace de travail afin de limiter davantage vos données.

   ![](assets/attrib_filter.png)

   >[!NOTE]
   >
   >Le jeu de formations est toujours composé de visiteurs qui remplissent la fenêtre de réussite. En filtrant à l’aide de l’éditeur de filtres, vous pouvez créer un sous-ensemble de visiteurs signalés dans la fenêtre Réussite.

1. Spécifiez des mesures de canal représentant des touches.

   Faites glisser les mesures vers la visualisation ou choisissez-les dans le [!DNL Inputs] > [!DNL Add Channel] . Si aucune mesure n’est déjà définie pour les campagnes ou les canaux, mais que les dimensions représentent les canaux, la visualisation peut automatiquement les créer avec la spécification d’une mesure tactile.

   Par exemple, avec la mesure tactile définie sur [!DNL Hits], et avec un [!DNL dimension] appel appelé [!DNL Media Type] avec des éléments qui incluent des éléments tels que [!DNL Email], [!DNL Press Release], [!DNL Print Ad]et [!DNL Social Media], la visualisation génère des mesures de canal du formulaire  lorsque vous faites glisser et déposez le ou les éléments sur la visualisation.[!DNL Hits where Media Type = Email]

1. Appuyez sur **Go**.

   Le processus d’analyse de l’ajustement optimal s’exécute et un graphique affiche les attributions par canal en fonction des entrées sélectionnées.

   >[!NOTE]
   >
   >Cliquez avec le bouton droit de la souris sur **Modèle terminé** sur l’analyse terminée pour afficher les statistiques du modèle d’attribution.

   ![](assets/attrib_visualization.png)

Une fois terminé, un graphique affiche un modèle d’attribution calculé par canal, ainsi qu’une distribution de la mesure *Recettes* (le cas échéant). Le modèle peut être enregistré en interne ou exporté vers d’autres systèmes.

>[!NOTE]
>
>**[!UICONTROL Streaming]**, **[!UICONTROL Online]** et **[!UICONTROL Offline]** les modes produisent des effets différents lors de la création d’un modèle d’attribution basé sur la latence des données évaluées. En mode Diffusion en continu, le **[!UICONTROL Model Complete]** message détaillé s’affiche. En mode En ligne et hors ligne, les détails **[!UICONTROL Local Model Complete]** s’affichent.

## Menu Options {#section-22288867f6c8483a8a38410f4b948346}

Le menu **Options** propose des fonctionnalités avancées pour configurer et afficher l’analyse des attributs Ajuster au mieux.

<table id="table_8F6F517B7DBF4259814BEC6D07A72EAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Menu Options </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Définir le filtre de formation </span> </td> 
   <td colname="col2"> Le filtre de formation est utilisé avec la fenêtre de réussite pour filtrer la population lors de la création du modèle d’attribution. Vous obtenez ainsi un sous-ensemble de données qui comprend uniquement les visiteurs que vous souhaitez analyser. <p>Remarque : Les utilisateurs chevronnés peuvent également tirer parti de la flexibilité des filtres pour se concentrer au-delà de la ligne temporelle des fenêtres de succès et de contact. Par exemple, en plus de sélectionner une plage de temps, vous pouvez sélectionner un ensemble de domaines <i></i> référents pour examiner uniquement l’attribution pour les utilisateurs de ces domaines. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Afficher la description du filtre complexe </span> </td> 
   <td colname="col2"> Affiche le code de filtre pour le filtre de formation, la fenêtre de réussite et la fenêtre tactile. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Enregistrer le modèle </span> </td> 
   <td colname="col2"> Enregistre le modèle d’attribution actuel en vue d’une utilisation ultérieure. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Charger le modèle </span> </td> 
   <td colname="col2"> Ouvre un modèle d’attribution précédemment enregistré. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Présentation </span> </td> 
   <td colname="col2"> Masque la barre de menus supérieure pour la présentation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Options &gt; Avancé</b> comprend des fonctionnalités permettant de définir la taille du jeu de formations et de spécifier l’approche à adopter en cas de déséquilibre de classe. </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Avancé &gt; Taille du jeu de formations </span> </td> 
   <td colname="col2"> <p>Définit la taille de l’ensemble de formations. </p> <p>Remarque :  La taille d’identification par défaut est Grande pour 250 000 visiteurs. </p> 
    <ul id="ul_5F17C60227C34A85A2C476A32F2B5DCD"> 
     <li id="li_A076FC2AD0214ADDBFCFD82AEA5F0880">Minuscule = 50 000 </li> 
     <li id="li_17E77E01D5374068BEBC80B3AD4CCD41">Petit = 75 000 </li> 
     <li id="li_7F6B4834742A4BFCBC3DB214425B88C3">Normal = 100 000 </li> 
     <li id="li_0BB7F791603745028CFC661EBC94D8B4">Large = 250,00 </li> 
     <li id="li_34B60233C84F48F1BCB8040C5195411A">Immense = 500 000 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Avancé &gt; Solde classe </b> </td> 
   <td colname="col2"> <p>Identifie et définit le nombre d’enregistrements d’entrée à générer pour un problème de déséquilibre de classe en fonction de la taille du jeu de données. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Options Réinitialiser et supprimer | Description |
|---|---|
| **[!UICONTROL Reset Model]** | Dans le **[!UICONTROL Reset]** menu, sélectionnez **[!UICONTROL Reset Model]** pour effacer la visualisation tout en conservant les mesures d’entrée. |
| **[!UICONTROL Reset All]** | Dans le **[!UICONTROL Reset]** menu, sélectionnez **[!UICONTROL Reset All]** pour effacer la visualisation et les mesures d’entrée. |
| **[!UICONTROL Remove]** | Cliquez avec le bouton droit sur une entrée et sélectionnez **[!UICONTROL Remove]** pour effacer la mesure de l’entrée sélectionnée. |
| **[!UICONTROL Remove All]** | Cliquez avec le bouton droit sur *Canaux* et sélectionnez **[!UICONTROL Remove All]** pour effacer toutes les mesures d’entrée. |

