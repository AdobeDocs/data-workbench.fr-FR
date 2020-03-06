---
description: Vous pouvez saisir du texte ou des expressions dans n’importe quelle cellule d’une feuille de calcul.
solution: Analytics
title: Utilisation des données dans les feuilles de calcul
topic: Data workbench
uuid: c2331fa5-aa07-4622-8f44-5124c22dffcb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Utilisation des données dans les feuilles de calcul{#work-with-data-in-worksheets}

Vous pouvez saisir du texte ou des expressions dans n’importe quelle cellule d’une feuille de calcul.

Toutes les expressions d’une feuille de calcul sont précédées d’un signe égal (=), sauf si vous utilisez [!DNL eval( )], ce qui traite le texte de la cellule référencée comme une expression.

Pour obtenir la liste complète des règles de syntaxe de mesure, de dimension et de filtre, voir Syntaxe [du langage de](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)requête.

**Pour saisir des données dans une feuille de calcul**

1. Cliquez deux fois sur une cellule de la feuille de calcul pour passer en mode d’édition. La cellule sélectionnée est mise en surbrillance.
1. Tapez ou collez les données de votre choix dans la cellule.

**Pour copier et coller d’une cellule à une autre**

1. Cliquez avec le bouton droit sur la cellule contenant les données à copier, puis cliquez sur **[!UICONTROL Copy]**.
1. Cliquez avec le bouton droit sur la cellule dans laquelle vous souhaitez coller les données copiées, puis cliquez sur **[!UICONTROL Paste]**.

Les outils de données mettent automatiquement à jour les références dans la nouvelle cellule afin de faire référence aux colonnes et aux lignes appropriées.

**Pour copier et coller d’un groupe de cellules vers un autre**

1. Sélectionnez les cellules contenant les données à copier.
1. Cliquez avec le bouton droit sur les cellules contenant les données à copier, puis cliquez sur **[!UICONTROL Copy]**.
1. Cliquez avec le bouton droit sur la première cellule dans laquelle vous souhaitez commencer à coller les données copiées, puis cliquez sur **[!UICONTROL Paste]**. Les données sont collées dans la première cellule et au-dessous.

Les outils de données mettent automatiquement à jour les références dans la nouvelle cellule afin de faire référence aux colonnes et aux lignes appropriées.

**Pour insérer une colonne**

* Cliquez avec le bouton droit sur une colonne et cliquez sur **[!UICONTROL Insert Column]**. La nouvelle colonne est insérée à gauche de la colonne sélectionnée.

**Pour supprimer une colonne**

* Cliquez avec le bouton droit sur la colonne à supprimer, puis cliquez sur **[!UICONTROL Delete Column]**. La colonne est supprimée.

**Pour insérer une ligne**

* Cliquez avec le bouton droit sur une ligne et cliquez sur **[!UICONTROL Insert Row]**. La nouvelle ligne est insérée au-dessus de la ligne sélectionnée.

**Pour supprimer une ligne**

* Cliquez avec le bouton droit sur la ligne à supprimer, puis cliquez sur **[!UICONTROL Delete Row]**. La ligne est supprimée.

**Pour redimensionner une colonne**

1. Dans la rangée d’en-tête de colonne, placez le curseur sur la ligne de séparation à droite de la colonne dont vous souhaitez modifier la taille.
1. Cliquez et faites glisser vers la droite pour augmenter la largeur de la colonne ou vers la gauche pour réduire la largeur de la colonne.

**Pour formater une cellule**

1. Cliquez avec le bouton droit de la souris sur la cellule et cliquez sur **[!UICONTROL Format]**.

   ![](assets/mnu_Worksheet_Format.png)

1. Cliquez sur le format souhaité dans le menu des options disponibles :

<table id="table_5788E01E52CC44E7927A0D23760D9EDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option de menu </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nombre </p> </td> 
   <td colname="col2"> <p>Applique le format numérique sélectionné à vos données (heure, date, pourcentage ou décimal, par exemple). </p> <p>Cliquez sur <span class="uicontrol"> Par défaut</span> pour supprimer la mise en forme sélectionnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Justifier </p> </td> 
   <td colname="col2"> <p>Justifie les données de la cellule à gauche, au centre ou à droite. La justification par défaut est laissée. </p> <p>Cliquez sur <span class="uicontrol"> Par défaut</span> pour supprimer la mise en forme sélectionnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Couleur </p> </td> 
   <td colname="col2"> <p>Applique la couleur de police sélectionnée aux données de la cellule. La couleur de police par défaut est le blanc. </p> <p>Cliquez sur <span class="uicontrol"> Par défaut</span> pour supprimer la mise en forme sélectionnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indicateur </p> </td> 
   <td colname="col2"> <p>Crée un indicateur de mesure à l’aide de cette cellule. Pour plus d’informations, voir <a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#concept-f0e911b23b2c4e8da3e1ea7b9ae04183"> Création d’indicateurs</a>de mesure. </p> <p>Cliquez sur <span class="uicontrol"> Par défaut</span> pour supprimer la mise en forme sélectionnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cellule d’entrée </p> </td> 
   <td colname="col2"> <p>Transforme la cellule sélectionnée en cellule d’entrée. Pour plus d’informations, voir <a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-input-cells.md#concept-08cd2c05a28a43dd9f7698b37e23e590"> Création de cellules</a>d’entrée. </p> <p>Cliquez sur <span class="uicontrol"> Par défaut</span> pour supprimer la mise en forme sélectionnée. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Raccourcis clavier {#section-05301f4d2c60418e86902635a7aeee20}

Dans les feuilles de calcul, vous pouvez utiliser la plupart des raccourcis clavier de modification de base que vous pouvez utiliser dans n’importe quel éditeur de texte, comme le Bloc-notes ou Microsoft Word.

Le tableau suivant répertorie les raccourcis clavier de base que vous pouvez utiliser lors de la saisie de données dans une feuille de calcul.

<table id="table_8E6F73F253B3451CA1DE45EE4F4E69EF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Raccourci </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Touches fléchées </p> </td> 
   <td colname="col2"> <p>Passez d’une cellule à une autre dans votre feuille de calcul à l’aide des touches fléchées Haut, Bas, Gauche et Droite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F2 </p> </td> 
   <td colname="col2"> <p>Modifiez la cellule en plaçant votre curseur dans la cellule que vous avez sélectionnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Entrée </p> </td> 
   <td colname="col2"> <p>Termine la modification de la cellule que vous avez sélectionnée. Le curseur est supprimé de la cellule et le contenu de la cellule reflète votre modification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Echap </p> </td> 
   <td colname="col2"> <p>Annule la modification de la cellule sélectionnée. Le curseur est supprimé de la cellule et le contenu de la cellule revient à ce qu’il était avant que vous ne commenciez à le modifier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Supprimer </p> </td> 
   <td colname="col2"> <p>Supprimez le contenu des cellules. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+A </p> </td> 
   <td colname="col2"> <p>Sélectionnez le contenu de la cellule. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+c </p> </td> 
   <td colname="col2"> <p>Copiez le contenu des cellules. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+x </p> <p>Maj+Supprimer </p> </td> 
   <td colname="col2"> <p>Copiez et supprimez le contenu des cellules. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+v </p> <p>Maj+Insérer </p> </td> 
   <td colname="col2"> <p>Collez le contenu des cellules que vous avez copiées dans les cellules sélectionnées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+z </p> </td> 
   <td colname="col2"> <p>Annule la saisie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+Maj+z </p> </td> 
   <td colname="col2"> <p>Rétablir la saisie. </p> </td> 
  </tr> 
 </tbody> 
</table>

