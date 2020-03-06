---
description: Vous pouvez utiliser des feuilles de calcul pour indiquer qu’une mesure a atteint un seuil défini.
solution: Analytics
title: Création d’un indicateur de mesure
topic: Data workbench
uuid: da304004-ef45-4c89-8c91-dd5158172dd6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Création d’un indicateur de mesure{#create-a-metric-indicator}

Vous pouvez utiliser des feuilles de calcul pour indiquer qu’une mesure a atteint un seuil défini.

En outre, vous pouvez utiliser [!DNL Report] pour générer et distribuer automatiquement un rapport lorsqu’une mesure atteint un seuil défini au cours d’une période donnée.

Pour plus d’informations sur [!DNL Report]cette solution, consultez le Guide *des rapports des outils de* données.

* [Indicateur Haut ou Bas](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)
* [Indicateur de vérification](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)

**Pour créer un indicateur de mesure à l’aide d’une feuille de calcul**

1. Définissez le contenu des cellules de la feuille de calcul.

   1. Dans la colonne A, saisissez le nom de la mesure souhaitée (par exemple, [!DNL Visitors]).
   1. Dans la colonne B, entrez la valeur de la mesure souhaitée (par exemple, [!DNL =Visitors]).
   1. Dans la colonne C, entrez le seuil inférieur de la mesure.
   1. Dans la colonne D, entrez le seuil élevé de la mesure.
   1. Dans la colonne E, entrez une formule appropriée. Pour obtenir des exemples, reportez-vous à la section Indicateur [](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba) Haut ou Bas ou Indicateur [de](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)vérification.
   1. Dans la cellule de formule (Colonne E), cliquez avec le bouton droit de la souris et cliquez sur **[!UICONTROL Format]** > **[!UICONTROL Indicator]**, puis cliquez sur l’une des options suivantes :

      * **[!UICONTROL None]**: Répertorie le calcul exact au lieu d’un indicateur.
      * **[!UICONTROL Check]**: Utilisez une coche ou un X pour indiquer que la valeur est supérieure ou inférieure au seuil que vous avez défini, selon votre formule. Voir [Indicateur](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)de vérification.
      * **[!UICONTROL Up or Down]**: Utilise une flèche vers le haut ou vers le bas pour indiquer si la valeur est inférieure au seuil inférieur (flèche vers le bas), supérieure au seuil supérieur (flèche vers le haut) ou entre les seuils inférieur et supérieur (vide). Voir Indicateur [](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)Haut ou Bas.

1. Répétez l’étape 1 pour les autres mesures pour lesquelles vous souhaitez créer des indicateurs.

La feuille de calcul obtenue ressemblerait à l’exemple suivant :

![](assets/vis_Worksheet_Alerts.png)

## Indicateur Haut ou Bas {#section-40d7a2c3df0d40d4a7bb1a7e856abcba}

Pour le [!DNL Up] ou [!DNL Down indicator], utilisez la formule suivante :

[!DNL (metric value - low threshold)/(high threshold - low threshold)*2 - 1]

Par exemple : [!DNL =(b2-c2)/(d2-c2)*2-1]

Trois résultats sont possibles pour chaque mesure lorsque vous utilisez cette formule avec [!DNL Up] ou [!DNL Down indicator]:

* Si la valeur de la mesure est comprise entre les seuils inférieur et supérieur, la formule renvoie un nombre compris entre -1 et 1 (uniquement). La flèche vers le haut ou vers le bas ne s&#39;affiche pas dans la feuille de calcul.
* Si la valeur de la mesure est inférieure ou égale au seuil inférieur, la formule renvoie une valeur inférieure ou égale à -1. L’indicateur de mesure se transforme en flèche vers le bas.
* Si la valeur de la mesure est supérieure ou égale au seuil supérieur, la formule renvoie un nombre supérieur ou égal à 1. L’indicateur de mesure se transforme en flèche vers le haut.

La feuille de calcul suivante illustre l’exemple de formule [!DNL =(b2-c2)/(d2-c2)*2-1] à afficher :

![](assets/vis_Worksheet_Alerts_UpDown.png)

## Indicateur de vérification {#section-98c5298a74f34dcbaaf151549fcc7090}

Pour le [!DNL Check indicator]rapport, vous utilisez une formule qui indique si vous souhaitez être averti lorsque la valeur de la mesure est supérieure ou inférieure au seuil que vous avez spécifié. Par exemple :

* Si vous souhaitez être averti lorsque la valeur est inférieure au seuil que vous avez défini, vous pouvez utiliser le format suivant :

   * [!DNL threshold - metric]

      Par exemple : [!DNL =(c2-b2)]

* Si vous souhaitez être averti lorsque la valeur est supérieure au seuil que vous avez défini, vous pouvez utiliser la formule suivante :

   * [!DNL metric - threshold]

      Par exemple : [!DNL =(b3-c3)]

Lorsqu’une coche s’affiche, la formule est évaluée à un nombre positif. Lorsqu’un X s’affiche, la formule est évaluée à un nombre négatif.

Il existe deux résultats possibles pour chaque mesure lors de l’utilisation [!DNL Check indicator]:

* Si la formule indique qu’il est souhaitable de maintenir la valeur de la mesure au-dessus du seuil, une coche s’affiche lorsque la valeur de la mesure est supérieure ou égale au seuil et un X s’affiche lorsque la valeur est inférieure au seuil.
* Si la formule indique qu’il est souhaitable de maintenir la valeur de la mesure en dessous du seuil, une coche s’affiche lorsque la valeur de la mesure est inférieure ou égale au seuil et un X s’affiche lorsque la valeur est supérieure au seuil.

La feuille de calcul suivante illustre les formules [!DNL =(c2-b2)] et [!DNL =(b3-c3)] les éléments à afficher :

![](assets/vis_Worksheet_Alerts_Check.png)

