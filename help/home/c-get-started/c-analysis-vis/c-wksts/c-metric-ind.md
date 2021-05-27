---
description: Vous pouvez utiliser des feuilles de calcul pour indiquer qu’une mesure a atteint un seuil défini.
title: Créer un indicateur de mesure
uuid: da304004-ef45-4c89-8c91-dd5158172dd6
exl-id: 5713f3dd-85ef-407c-b21c-80e9b4390b6d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 2%

---

# Créer un indicateur de mesure{#create-a-metric-indicator}

Vous pouvez utiliser des feuilles de calcul pour indiquer qu’une mesure a atteint un seuil défini.

En outre, vous pouvez utiliser [!DNL Report] pour générer et distribuer automatiquement un rapport lorsqu’une mesure atteint un seuil défini au cours d’une période spécifiée.

Pour plus d’informations sur [!DNL Report], consultez le *Guide du Data Workbench de rapports*.

* [Indicateur Haut ou Bas](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)
* [Indicateur de vérification](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)

**Pour créer un indicateur de mesure à l’aide d’une feuille de calcul**

1. Définissez le contenu des cellules de la feuille de calcul.

   1. Dans la colonne A, saisissez le nom de la mesure souhaitée (par exemple, [!DNL Visitors]).
   1. Dans la colonne B, saisissez la valeur de la mesure souhaitée (par exemple, [!DNL =Visitors]).
   1. Dans la colonne C, saisissez le seuil inférieur de la mesure.
   1. Dans la colonne D, entrez le seuil élevé de la mesure.
   1. Dans la colonne E, saisissez une formule appropriée. Pour obtenir des exemples, voir [Indicateur de haut ou de bas](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba) ou [Indicateur de vérification](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090).
   1. Dans la cellule de formule (Colonne E), cliquez avec le bouton droit de la souris et cliquez sur **[!UICONTROL Format]** > **[!UICONTROL Indicator]**, puis cliquez sur l’une des options suivantes :

      * **[!UICONTROL None]**: Répertorie le calcul exact au lieu d’un indicateur.
      * **[!UICONTROL Check]**: Utilisez une coche ou un X pour indiquer que la valeur est supérieure ou inférieure au seuil que vous avez défini, selon votre formule. Voir [Vérification de l’indicateur](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090).
      * **[!UICONTROL Up or Down]**: Utilise une flèche vers le haut ou vers le bas pour indiquer si la valeur est inférieure au seuil faible (flèche vers le bas), au-dessus du seuil élevé (flèche vers le haut) ou entre les seuils bas et élevé (vide). Voir [Indicateur haut ou bas](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba).

1. Répétez l’étape 1 pour les autres mesures pour lesquelles vous souhaitez créer des indicateurs.

La feuille de calcul obtenue ressemble à l’exemple suivant :

![](assets/vis_Worksheet_Alerts.png)

## Indicateur de haut ou de bas {#section-40d7a2c3df0d40d4a7bb1a7e856abcba}

Pour [!DNL Up] ou [!DNL Down indicator], utilisez la formule suivante :

[!DNL (metric value - low threshold)/(high threshold - low threshold)*2 - 1]

Par exemple : [!DNL =(b2-c2)/(d2-c2)*2-1]

Trois résultats sont possibles pour chaque mesure lors de l’utilisation de cette formule avec [!DNL Up] ou [!DNL Down indicator] :

* Si la valeur de la mesure est comprise entre les seuils inférieur et élevé, la formule évalue un nombre compris entre -1 et 1 (exclusivement). La flèche vers le haut ou vers le bas ne s’affiche pas dans la feuille de calcul.
* Si la valeur de la mesure est inférieure ou égale au seuil inférieur, la formule évalue à une valeur inférieure ou égale à -1. L’indicateur de mesure se transforme en flèche vers le bas.
* Si la valeur de la mesure est supérieure ou égale au seuil élevé, la formule évalue à un nombre supérieur ou égal à 1. L’indicateur de mesure se transforme en flèche vers le haut.

La feuille de calcul suivante illustre l’affichage de l’exemple de formule [!DNL =(b2-c2)/(d2-c2)*2-1] :

![](assets/vis_Worksheet_Alerts_UpDown.png)

## Indicateur de vérification {#section-98c5298a74f34dcbaaf151549fcc7090}

Pour la balise [!DNL Check indicator], vous utilisez une formule qui indique si vous souhaitez être averti lorsque la valeur de la mesure est supérieure ou inférieure au seuil que vous spécifiez. Par exemple :

* Si vous souhaitez être averti lorsque la valeur est inférieure au seuil que vous avez défini, vous pouvez utiliser le format suivant :

   * [!DNL threshold - metric]

      Par exemple : [!DNL =(c2-b2)]

* Si vous souhaitez être averti lorsque la valeur est supérieure au seuil que vous avez défini, vous pouvez utiliser la formule suivante :

   * [!DNL metric - threshold]

      Par exemple : [!DNL =(b3-c3)]

Lorsqu’une coche s’affiche, la formule est évaluée sur un nombre positif. Lorsqu’un X s’affiche, la formule est évaluée à un nombre négatif.

Deux résultats sont possibles pour chaque mesure lors de l’utilisation de [!DNL Check indicator] :

* Si la formule indique que le fait de maintenir la valeur de la mesure au-dessus du seuil est souhaitable, une coche s’affiche lorsque la valeur de la mesure est supérieure ou égale au seuil, et un X s’affiche lorsque la valeur est inférieure au seuil.
* Si la formule indique que la conservation de la valeur de mesure en dessous du seuil est souhaitable, une coche s’affiche lorsque la valeur de mesure est inférieure ou égale au seuil, et une croix (X) s’affiche lorsque la valeur est supérieure au seuil.

La feuille de calcul suivante illustre les formules [!DNL =(c2-b2)] et [!DNL =(b3-c3)] qui s’affichent :

![](assets/vis_Worksheet_Alerts_Check.png)
