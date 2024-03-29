---
description: Ouvrez la fonction Attribution de l’ajustement optimal dans le menu Premium et procédez comme suit pour créer un modèle d’attribution de l’ajustement optimal.
title: Créer un modèle d’attribution d’ajustement optimal
uuid: d1fd0340-1917-41bc-9a08-e78a79d084e7
exl-id: e0a42374-2500-46a3-a72a-708ab2d228db
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 1%

---

# Créer un modèle d’attribution d’ajustement optimal{#build-a-best-fit-attribution-model}

{{eol}}

Ouvrez la fonction Attribution de l’ajustement optimal dans le menu Premium et procédez comme suit pour créer un modèle d’attribution de l’ajustement optimal.

Consultez un aperçu de la [Attribution de l’ajustement optimal](../../../../home/c-get-started/c-attribution-profiles/c-attrib-algorithmic/c-attrib-algorithmic.md#concept-237feb6e9c4d49efaf75399297dcb9d1).

1. Ouvrir **Attribution de l’ajustement optimal**.

   Ouvrez un espace de travail et cliquez sur **[!UICONTROL Premium]** > **[!UICONTROL Best Fit Attribution]**.

   ![](assets/attrib_windows_launch.png)

   >[!NOTE]
   >
   >L’attribution d’ajustement optimal est une fonction de Adobe Analytics Premium qui nécessite que vous activiez Premium dans votre profil. Vous devez mettre à jour votre certificat et ajouter le profil Premium à votre fichier profile.cfg . Voir [Mise à niveau du serveur DWB : 6.2 à 6.3](/help/home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md) pour DWB 6.3.

1. Définissez la variable **[!UICONTROL Success]** mesure.

   >[!NOTE]
   >
   >Vous pouvez soit faire glisser une mesure depuis un **[!UICONTROL Finder]** dans le volet de gauche de la visualisation d’attribution ou sélectionnez dans la **Entrées** .

   Cliquez sur **[!UICONTROL Inputs]** > **[!UICONTROL Set Success]**. Le menu des mesures s’ouvre. ![](assets/attrib_set_success_metric.png)

   Sélectionnez une mesure qui identifie une conversion réussie.

1. (facultatif) Définissez la variable **Recettes** mesure.

   Définissez une mesure pour évaluer les recettes tout au long du processus de conversion.

1. Définissez la variable **Touche** mesure.

   >[!NOTE]
   >
   >La définition d’une mesure tactile n’est nécessaire que si vous tentez de créer automatiquement des mesures de succès en faisant glisser des éléments de dimension sur la visualisation.

   Cliquez sur le bouton **[!UICONTROL Inputs]** et sélectionnez **Définir tactile** ou faites glisser une mesure à partir de l’outil de recherche. ![](assets/attrib_set_touch.png)

   Elle sera utilisée pour dériver des mesures de canal lorsque les éléments de dimension sont utilisés comme entrées.

1. Définir une **Succès** fenêtre.

   Cliquez sur [!DNL Inputs > Success Window]. Sélectionnez une période dans un tableau, puis nommez la fenêtre Succès. Cliquez sur **[!UICONTROL Workspace Selection]** et les dates sélectionnées seront affectées comme période pour la mesure de succès.

   ![](assets/attrib_set_success_window.png)

   >[!NOTE]
   >
   >La fenêtre de succès étant une sélection de poste de travail, vous pouvez inclure n’importe quelle(s) dimension(s) dans votre fenêtre de succès.

1. Définir une **[!UICONTROL Touch Window]**.

   Cliquez sur [!DNL Inputs > Touch Window]. Sélectionnez une plage de dates dans un tableau, puis nommez la fenêtre tactile. Cliquez sur **[!UICONTROL Workspace Selection]** et les dates sélectionnées seront affectées comme période pour la mesure de succès.

   ![](assets/attrib_set_touch_window.png)

   Par défaut, la variable **Touche** est définie sur la même période que la variable **[!UICONTROL Success]** fenêtre.

1. (facultatif) Définissez un filtre de formation.

   Vous pouvez également spécifier une **Filtre de formation** dans l’espace de travail pour filtrer les données du visiteur.

   >[!NOTE]
   >
   >Dans la définition des fenêtres Réussite et Touche, vous pouvez appliquer le filtre Formation aux sélections actuelles de l’espace de travail pour limiter davantage vos données.

   ![](assets/attrib_filter.png)

   >[!NOTE]
   >
   >Le jeu de formations est toujours composé de visiteurs qui correspondent à la fenêtre de succès. En filtrant à l’aide de l’éditeur de filtres, vous pouvez créer un sous-ensemble de visiteurs signalés dans la fenêtre Succès.

1. Spécifiez les mesures de canal qui représentent les touches.

   Faites glisser les mesures vers la visualisation ou sélectionnez-les dans la [!DNL Inputs] > [!DNL Add Channel] . Si aucune mesure n’est déjà définie pour les campagnes ou les canaux, mais que des dimensions représentent les canaux, la visualisation peut les créer automatiquement avec la spécification d’une mesure tactile.

   Par exemple, avec la mesure tactile définie sur [!DNL Hits], et une [!DNL dimension] appelé [!DNL Media Type] avec des éléments qui incluent des éléments tels que [!DNL Email], [!DNL Press Release], [!DNL Print Ad], et [!DNL Social Media], la visualisation génère les mesures de canal du formulaire. [!DNL Hits where Media Type = Email] lorsque vous faites glisser et déposez le ou les éléments sur la visualisation.

1. Press **Aller**.

   Le processus d’analyse de l’ajustement optimal s’exécute et un graphique affiche les attributions par canal en fonction des entrées sélectionnées.

   >[!NOTE]
   >
   >Clic droit **Fin du modèle** sur l’analyse terminée pour afficher les statistiques du modèle d’attribution.

   ![](assets/attrib_visualization.png)

Une fois l’opération terminée, un graphique affiche un modèle d’attribution calculé par canal, ainsi qu’une distribution de la variable *Recettes* (si définie). Le modèle peut être enregistré en interne ou exporté vers d’autres systèmes.

>[!NOTE]
>
>**[!UICONTROL Streaming]**, **[!UICONTROL Online]** et **[!UICONTROL Offline]** Les modes produisent des effets différents lors de la création d’un modèle d’attribution en fonction de la latence des données évaluées. En mode Diffusion en continu, le détail **[!UICONTROL Model Complete]** s’affiche. En modes en ligne et hors ligne, le détail **[!UICONTROL Local Model Complete]** s’affiche.

## Menu Options {#section-22288867f6c8483a8a38410f4b948346}

Le **Options** propose des fonctionnalités avancées pour configurer et afficher l’analyse de l’ajustement optimal.

<table id="table_8F6F517B7DBF4259814BEC6D07A72EAC">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Menu Options </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"><span class="uicontrol"> Définir le filtre d’entraînement </span> </td>
   <td colname="col2"> Le filtre de formation est utilisé avec la fenêtre de succès pour filtrer la population lors de la création du modèle d’attribution. Cela fournit un sous-ensemble de données qui inclut uniquement les visiteurs que vous souhaitez analyser. <p>Remarque : Les utilisateurs expérimentés peuvent également tirer parti de la flexibilité des filtres pour se concentrer au-delà de la ligne de temps des fenêtres de succès et tactile. Par exemple, en plus de sélectionner une période, vous pouvez sélectionner un ensemble de <i>Domaines référents</i> pour examiner uniquement l’attribution pour les utilisateurs de ces domaines. </p> </td>
  </tr>
  <tr>
   <td colname="col1"><span class="uicontrol"> Afficher la description de filtre complexe </span> </td>
   <td colname="col2"> Affiche le code de filtre pour le filtre de formation, la fenêtre de succès et la fenêtre tactile. </td>
  </tr>
  <tr>
   <td colname="col1"><span class="uicontrol"> Enregistrer le modèle </span> </td>
   <td colname="col2"> Enregistre le modèle d’attribution actuel en vue d’une utilisation ultérieure. </td>
  </tr>
  <tr>
   <td colname="col1"><span class="uicontrol"> Load Model </span> </td>
   <td colname="col2"> Ouvre un modèle d’attribution précédemment enregistré. </td>
  </tr>
  <tr>
   <td colname="col1"><span class="uicontrol"> Présentation </span> </td>
   <td colname="col2"> Masque la barre de menu supérieure pour la présentation. </td>
  </tr>
  <tr>
   <td colname="col1"> <p><b>Options &gt; Avancé</b> inclut des fonctionnalités permettant de définir la taille du jeu de formation et de spécifier l’approche à adopter en cas de déséquilibre de classe. </p> </td>
   <td colname="col2"> </td>
  </tr>
  <tr>
   <td colname="col1"><span class="uicontrol"> Avancé &gt; Taille du jeu de formation </span> </td>
   <td colname="col2"> <p>Définit la taille du jeu d’entraînement. </p> <p>Remarque : La taille de formation par défaut est Grande pour 250 000 visiteurs. </p>
    <ul id="ul_5F17C60227C34A85A2C476A32F2B5DCD">
     <li id="li_A076FC2AD0214ADDBFCFD82AEA5F0880">Minuscule = 50 000 </li>
     <li id="li_17E77E01D5374068BEBC80B3AD4CCD41">Petit = 75 000 </li>
     <li id="li_7F6B4834742A4BFCBC3DB214425B88C3">Normal = 100 000 </li>
     <li id="li_0BB7F791603745028CFC661EBC94D8B4">Grand = 250,00 </li>
     <li id="li_34B60233C84F48F1BCB8040C5195411A">Huge = 500 000 </li>
    </ul> </td>
  </tr>
  <tr>
   <td colname="col1"><b>Avancé &gt; Balance des classes </b> </td>
   <td colname="col2"> <p>Identifie et définit le nombre d’enregistrements d’entrée à générer pour un problème de déséquilibre de classe en fonction de la taille du jeu de données. </p> </td>
  </tr>
 </tbody>
</table>

| Options de réinitialisation et de suppression | Description |
|---|---|
| **[!UICONTROL Reset Model]** | Dans la **[!UICONTROL Reset]** menu, sélectionnez **[!UICONTROL Reset Model]** pour effacer la visualisation tout en conservant les mesures d’entrée. |
| **[!UICONTROL Reset All]** | Dans la **[!UICONTROL Reset]** menu, sélectionnez **[!UICONTROL Reset All]** pour effacer la visualisation et les mesures d’entrée. |
| **[!UICONTROL Remove]** | Cliquez avec le bouton droit de la souris sur une entrée et sélectionnez **[!UICONTROL Remove]** pour effacer la mesure de l’entrée sélectionnée. |
| **[!UICONTROL Remove All]** | Cliquez avec le bouton droit de la souris sur *Canaux* et sélectionnez **[!UICONTROL Remove All]** pour effacer toutes les mesures d’entrée. |
