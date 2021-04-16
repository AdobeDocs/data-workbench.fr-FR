---
description: Les incrustations de page sont configurées uniquement dans l’application Site, mais elles peuvent être configurées pour d’autres applications.
title: Configurer une superposition des pages
uuid: c4c612ed-5154-4b20-96ab-24b74fba19a2
exl-id: 4e0dfce8-def2-49f3-93e8-41d82922fb88
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 1%

---

# Configurer une superposition des pages{#configure-a-page-overlay}

Les incrustations de page sont configurées uniquement dans l’application Site, mais elles peuvent être configurées pour d’autres applications.

Pour plus d’informations sur la configuration d’une incrustation de page pour une autre application, contactez les services de conseil en Adobe.

La visualisation en incrustation de page est un outil d’analyse des liens HTML. Lorsque vous demandez une incrustation pour une page particulière, le Data Workbench prend un instantané de la page réelle telle qu’elle apparaîtrait dans un navigateur Web et analyse le code HTML qui représente les liens selon une liste d’expressions régulières que vous définissez. Pour chaque lien de la page sélectionnée, le logiciel tente de trouver une correspondance de modèle d&#39;expression standard en travaillant sur la liste jusqu&#39;à ce que la première correspondance soit trouvée. S’il existe une correspondance, le lien s’affiche en surbrillance dans l’incrustation de page.

L’incrustation de page affiche les données uniquement lorsque vous ajoutez une légende de couleur à l’espace de travail contenant l’incrustation de page.

>[!NOTE]
>
>La configuration de l’incrustation de page nécessite un travail de configuration minutieux et il est possible de créer des résultats trompeurs si les liens sont incorrectement mappés aux données. Le travail de configuration de l’incrustation de page pour un site spécifique dépend de la manière dont les liens sont présentés dans le code HTML des pages du site.

Par sa nature, l’incrustation de page suggère à l’utilisateur le modèle mental qu’elle affiche &quot;où les utilisateurs cliquent&quot;. Si les données qui soutiennent la visualisation ne correspondent pas à ce modèle, le risque de confusion est élevé.

Dans [!DNL Site], un lien représente généralement un élément de la dimension URI suivant ou Lien suivant, mais vous pouvez mapper un lien à n’importe quelle dimension logique pour votre analyse. Pour plus d’informations sur la configuration de l’incrustation de page pour d’autres dimensions, contactez les services de conseil en Adobe.

>[!NOTE]
>
>Il n’est pas recommandé d’utiliser la dimension Page pour l’incrustation de page. Les utilisateurs peuvent renommer les éléments des dimensions Page, modifiant ainsi la syntaxe des liens sur laquelle repose la fonctionnalité d’incrustation de page.

Pour configurer l’incrustation de page pour [!DNL Site], vous devez modifier deux fichiers :

* **[!DNL Page Overlay.vw]:** Ce fichier est un fichier de modèle destiné à la création de visualisations d’incrustation de page. Au moins un fichier de modèle doit être présent dans le profil pour lequel vous configurez l’incrustation de page.
* **[!DNL Page Overlay Link Templates.cfg]:** Lorsque la visualisation de l’incrustation de page charge une page, elle identifie automatiquement les liens de la page et leurs destinations. Pour relier ces liens aux éléments des données, vous devez définir un ensemble d&#39;expressions régulières dans ce fichier.

   Vous pouvez définir plusieurs expressions régulières à faire correspondre par rapport aux éléments de la dimension. L&#39;ordre dans lequel vous définissez les expressions est important. Lorsque vous demandez une incrustation pour une page particulière, le Data Workbench prend un instantané de la page réelle telle qu’elle apparaîtrait dans un navigateur Web et analyse le code HTML qui représente les liens selon une liste d’expressions régulières que vous définissez. Pour chaque lien de la page sélectionnée, le logiciel tente de trouver une correspondance de modèle d&#39;expression standard en travaillant sur la liste jusqu&#39;à ce que la première correspondance soit trouvée. La première expression à faire correspondre un élément de dimension est celle utilisée. Par conséquent, il est préférable de liste d&#39;abord l&#39;expression régulière avec le modèle de correspondance le plus spécifique, suivi d&#39;expressions moins spécifiques. S’il existe une correspondance, le lien s’affiche en surbrillance dans la visualisation de l’incrustation de page.

**Pour configurer l’incrustation de page pour le site**

1. I

   Dans [!DNL Profile Manager], accédez à **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.

   >[!NOTE]
   >
   >Le répertoire Eléments de Dimension contient les éléments de menu contextuel qui s’affichent lorsque vous cliquez avec le bouton droit de la souris sur un élément de dimension. Par exemple, ouvrez une table URI, puis sélectionnez un élément URI. Cliquez avec le bouton droit de la souris sur l’URI et l’incrustation de page s’affiche.

1. Dans le dossier URI, cliquez avec le bouton droit de la souris sur la coche en regard du fichier [!DNL Page Overlay.vw] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Spécifiez le domaine (et la hauteur du navigateur, si nécessaire).

   ```
   window = simpleBorderWindow: 
     client = scrollWindow: 
       client = PageOverlay: 
         URI Template = string: http://%Domain%%Element%
         URI Parameters = map: 
           Domain = string: domain name
           Element = ref: Element/Name
         Dim = ref: wdata/model/dim/URI
         Dim Element = ref: Element/Name
         Level = ref: wdata/model/dim/Page View
         Group = ref: wdata/model/dim/Session
         Browser Height = int: browser height
     pos = v3d: (518, 202, 0)
     size = v3d: (810, 610, 0)
     titleBar = editor: 
       size = v3d: (61, 19, 0)
       text = string: 
   ```

1. Enregistrez le fichier.
1. Pour mettre cette modification à la disposition de tous les utilisateurs du profil de travail, dans le [!DNL Profile Manager], cochez la case du fichier [!DNL .vw] dans la colonne [!DNL User], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.

   >[!NOTE]
   >
   >Vous pouvez créer des fichiers de modèle supplémentaires pour d’autres sites ou sous-domaines. Chaque modèle que vous créez apparaît dans le [!DNL Page Overlay menu].

1. Dans le dossier Contexte de [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche en regard du fichier [!DNL Page Overlay Link Templates.cfg] et cliquez sur **[!UICONTROL Make Local]**.

   Une coche pour ce fichier apparaît dans la colonne [!DNL User].

1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Cliquez avec le bouton droit **[!UICONTROL Link Templates]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.
1. Modifiez les paramètres du vecteur LinkRegex si nécessaire :

<table id="table_24DD4BB5009542F7BB1DA3318E2E6E2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour ce paramètre... </th> 
   <th colname="col2" class="entry"> Fournissez ces informations... </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Dimension </p> </td> 
   <td colname="col2"> <p>Dimension (généralement la dimension URI suivante) représentée par le lien. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expression </p> </td> 
   <td colname="col2"> <p>Expression régulière utilisée pour sélectionner la partie appropriée du lien HTML afin de trouver l’élément suivant dans la Dimension. L’expression régulière doit correspondre exactement et le modèle de sortie souhaité est regroupé avec des parenthèses. Pour plus d'informations sur les expressions régulières, consultez le <i>Guide de configuration des ensembles de données</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modèle de sortie </p> </td> 
   <td colname="col2"> <p>Modèle de sortie de l’expression régulière utilisée pour extraire l’élément obtenu du paramètre de Dimension. </p> </td> 
  </tr> 
 </tbody> 
</table>

L’exemple de fichier suivant montre trois expressions régulières :

![](assets/cfg_PageOverlayLinkTemplates_Example.png)

1. Pour enregistrer le fichier, cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.
1. Pour mettre cette modification à la disposition de tous les utilisateurs du profil de travail, cochez la case [!DNL Page Overlay Link Templates.cfg] dans la colonne [!DNL User] et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.
