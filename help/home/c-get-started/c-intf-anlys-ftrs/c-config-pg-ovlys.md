---
description: Les superpositions de page sont configurées uniquement dans l’application Site, mais elles peuvent être configurées pour d’autres applications.
title: Configurer une superposition des pages
uuid: c4c612ed-5154-4b20-96ab-24b74fba19a2
exl-id: 4e0dfce8-def2-49f3-93e8-41d82922fb88
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 1%

---

# Configurer une superposition des pages{#configure-a-page-overlay}

{{eol}}

Les superpositions de page sont configurées uniquement dans l’application Site, mais elles peuvent être configurées pour d’autres applications.

Pour plus d’informations sur la configuration de superposition de page pour une autre application, contactez les services de conseil d’Adobe.

La visualisation de superposition de page est un outil d’analyse des liens de HTML. Lorsque vous demandez une superposition pour une page spécifique, Data Workbench prend un instantané de la page telle qu’elle apparaîtrait dans un navigateur web et analyse le code de HTML qui représente les liens en fonction d’une liste d’expressions régulières que vous définissez. Pour chaque lien de la page sélectionnée, le logiciel tente de trouver une correspondance de modèle d’expression régulière en travaillant dans la liste jusqu’à ce que la première correspondance soit trouvée. S’il existe une correspondance, le lien apparaît en surbrillance dans la superposition de la page.

La superposition de page affiche les données uniquement lorsque vous ajoutez une légende de couleur à l’espace de travail contenant la superposition de page.

>[!NOTE]
>
>La configuration de la superposition des pages nécessite un travail de configuration minutieux et il est possible de créer des résultats trompeurs si les liens sont mappés de manière inappropriée aux données. Le travail nécessaire à la configuration de la superposition de pages pour un site spécifique dépend de la manière dont les liens sont présentés dans le code de HTML des pages du site.

Par nature, la superposition de page suggère à l’utilisateur le modèle mental qu’il affiche &quot;lorsque les gens cliquent&quot;. Si les données qui soutiennent la visualisation ne correspondent pas à ce modèle, le risque de confusion est élevé.

Dans [!DNL Site], un lien représente généralement un élément de la dimension URI suivant ou Lien suivant , mais vous pouvez associer un lien à n’importe quelle dimension logique pour votre analyse. Pour plus d’informations sur la configuration de la superposition de pages pour d’autres dimensions, contactez les services de conseil d’Adobe.

>[!NOTE]
>
>L’utilisation de la dimension Page pour la superposition de page n’est pas recommandée. Les utilisateurs peuvent renommer les éléments des dimensions Page, modifiant ainsi la syntaxe des liens sur lesquels repose la fonctionnalité de superposition de page.

Pour configurer une superposition de page pour [!DNL Site], vous devez modifier deux fichiers :

* **[!DNL Page Overlay.vw]:** Ce fichier est un fichier modèle permettant de créer des visualisations de superposition de page. Au moins un fichier de modèle doit être présent dans le profil pour lequel vous configurez la superposition des pages.
* **[!DNL Page Overlay Link Templates.cfg]:** Lorsque la visualisation de superposition de page charge une page, elle identifie automatiquement les liens de la page et leurs destinations. Pour relier ces liens aux éléments des données, vous devez définir un ensemble d&#39;expressions régulières dans ce fichier.

   Vous pouvez définir plusieurs expressions régulières à faire correspondre par rapport aux éléments de la dimension. L’ordre dans lequel vous définissez les expressions est important. Lorsque vous demandez une superposition pour une page spécifique, Data Workbench prend un instantané de la page telle qu’elle apparaîtrait dans un navigateur web et analyse le code de HTML qui représente les liens en fonction d’une liste d’expressions régulières que vous définissez. Pour chaque lien de la page sélectionnée, le logiciel tente de trouver une correspondance de modèle d’expression régulière en travaillant dans la liste jusqu’à ce que la première correspondance soit trouvée. La première expression qui correspond à un élément de dimension est celle utilisée. Par conséquent, il est préférable de lister d’abord l’expression régulière avec le modèle de correspondance le plus spécifique, suivi d’expressions moins spécifiques. S’il existe une correspondance, le lien apparaît en surbrillance dans la visualisation de superposition de page.

**Pour configurer la superposition de pages pour le site**

1. I

   n [!DNL Profile Manager], accédez à **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.

   >[!NOTE]
   >
   >Le répertoire des éléments de Dimension contient les éléments de menu contextuel qui s’affichent lorsque vous cliquez avec le bouton droit de la souris sur un élément de dimension. Par exemple, ouvrez un tableau URI, puis sélectionnez un élément URI. Cliquez avec le bouton droit de la souris sur l’URI et l’incrustation de page s’affiche.

1. Dans le dossier URI, cliquez avec le bouton droit de la souris sur la coche située en regard de l’objet [!DNL Page Overlay.vw] et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la variable [!DNL User] colonne .
1. Cliquez avec le bouton droit de la souris sur la coche que vous venez de créer, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Indiquez le domaine (et la hauteur du navigateur, si nécessaire).

   ```
   window = simpleBorderWindow:
     client = scrollWindow:
       client = PageOverlay:
         URI Template = string: https://%Domain%%Element%
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
1. Pour mettre cette modification à la disposition de tous les utilisateurs du profil de travail, dans la variable [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche correspondant au [!DNL .vw] dans le fichier [!DNL User] et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >Vous pouvez créer des fichiers de modèle supplémentaires pour d’autres sites ou sous-domaines. Chaque modèle que vous créez apparaît dans le [!DNL Page Overlay menu].

1. Dans le dossier Context du [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche en regard de l’option [!DNL Page Overlay Link Templates.cfg] et cliquez sur **[!UICONTROL Make Local]**.

   Une coche pour ce fichier apparaît dans la variable [!DNL User] colonne .

1. Cliquez avec le bouton droit de la souris sur la coche que vous venez de créer, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Clic droit **[!UICONTROL Link Templates]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.
1. Modifiez les paramètres du vecteur LinkRegex selon les besoins :

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
   <td colname="col2"> <p>Dimension (généralement la dimension URI suivant) représentée par le lien. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Expression </p> </td>
   <td colname="col2"> <p>Expression régulière utilisée pour sélectionner la partie appropriée du lien du HTML pour trouver l’élément suivant dans la Dimension. L’expression régulière doit correspondre exactement et le modèle de sortie souhaité est regroupé avec des parenthèses. Pour plus d’informations sur les expressions régulières, voir <i>Guide de configuration des jeux de données</i>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Modèle de sortie </p> </td>
   <td colname="col2"> <p>Modèle de sortie de l’expression régulière utilisé pour extraire l’élément obtenu du paramètre de Dimension. </p> </td>
  </tr>
 </tbody>
</table>

L’exemple de fichier suivant montre trois expressions régulières :

![](assets/cfg_PageOverlayLinkTemplates_Example.png)

1. Pour enregistrer le fichier, cliquez avec le bouton droit de la souris **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre, puis cliquez sur **[!UICONTROL Save]**.
1. Pour mettre cette modification à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche pour [!DNL Page Overlay Link Templates.cfg] dans le [!DNL User] et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
