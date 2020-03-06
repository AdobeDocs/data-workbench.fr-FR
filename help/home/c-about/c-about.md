---
description: Les mesures, dimensions et filtres fournissent une structure dans laquelle les calculs sont effectués sur les données traitées dans un jeu de données de l’outil de données.
solution: Analytics
title: Mesures, dimensions et filtres des outils de données
topic: Data workbench
uuid: 3c0300a0-ae19-4817-aab8-7294e0eabdd9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mesures, dimensions et filtres des outils de données{#data-workbench-metrics-dimensions-and-filters}

Les mesures, dimensions et filtres fournissent une structure dans laquelle les calculs sont effectués sur les données traitées dans un jeu de données de l’outil de données.

Les résultats des calculs définis à l’aide de cette structure s’affichent dans les espaces de travail, les tableaux de bord, les rapports ou d’autres sorties. En bref, tout nombre affiché dans ou à partir d’une application est le résultat d’une requête d’un jeu de données qui implique une mesure, une dimension et un filtre.

Au niveau le plus élémentaire, une mesure décrit ce qui est calculé à partir du jeu de données et à son sujet, une dimension ventile les données du jeu de données en catégories et un filtre décrit une partie ou un sous-ensemble sélectionné des données du jeu de données.

Lorsque le serveur Outils de données traite les données pour créer un jeu de données, les dimensions des données sont créées, puis mises à jour en permanence au fur et à mesure que de nouvelles données sont lues et traitées par le serveur. Les mesures et les filtres sont calculés à partir de ces dimensions de données.

>[!CAUTION]
>
>Si vous redéfinissez une mesure interne, le système se comporte de manière inattendue en raison d’une valeur incorrecte. Vos rapports ne seront pas générés à moins qu’une mesure ne lise 100 %. Il est recommandé de ne pas modifier les définitions de mesure.

## Exemple {#section-ecc465d1a5e34d559c1983e96fa409ec}

Imaginez un jeu de données qui contient des informations sur toutes les personnes dans le monde. Cet ensemble de données contient, au minimum, toutes les personnes dans le monde et leur âge. Une mesure utile à calculer à partir de ce jeu de données serait Age moyen. L’évaluation de cette mesure générerait un nombre : l’âge moyen de la population mondiale.

L’ajout d’une dimension au jeu de données rend ces informations plus utiles et plus gérables. Si l’ensemble de données contient également le pays de résidence de chaque personne, la définition d’une dimension Pays permettrait de segmenter les personnes en groupes pour chaque pays du monde. L’évaluation de la mesure Age moyen par rapport à la dimension Pays donnerait une liste de nombres, un pour chaque pays, représentant chacun l’âge moyen des personnes dans ce pays.

L’application d’un filtre (ou filtre de sélection) dans une formule de mesure peut fournir des informations plus détaillées ou permettre la définition d’une nouvelle mesure en fonction de mesures et de dimensions existantes. L’évaluation de la mesure Age moyen avec un filtre &quot;où pays est égal à Suède&quot; génère un nombre : l&#39;âge moyen des personnes en Suède. Une mesure basée sur ce filtre pourrait être l’âge moyen suédois.

Par exemple :

```
Swedish_Average_Age=Average_Age[country = ‘Sweden’]
```

## Comment les mesures, les dimensions et les filtres sont liés {#section-28622596124140b280e6b993b174ef84}

En général, l’évaluation d’une mesure sur une dimension conduit à l’évaluation de cette mesure pour chaque élément (ou élément) de dimension. Dans l’exemple ci-dessus, la dimension Pays comporte un élément pour chaque pays du monde. L&#39;évaluation de l&#39;âge moyen par pays donnerait l&#39;âge moyen pour chacun des éléments (pays), y compris l&#39;élément Suède.

Il est important de noter que lorsque vous évaluez une mesure sur une dimension, vous recevez le même résultat numérique pour un élément de dimension spécifique, que vous évaluiez cette mesure pour l’ensemble de la dimension ou que vous définissiez un filtre correspondant à cet élément de dimension spécifique. Dans l’exemple précédent, lorsque vous recherchez l’âge moyen des personnes en Suède, l’une des méthodes suivantes donne des résultats identiques :

* Evaluez la mesure Age moyen sur la dimension Pays, puis examinez le nombre de l’élément de dimension Suède.
* Evaluez la mesure Age moyen avec un filtre &quot;personnes en Suède&quot; (exprimé sous la forme [!DNL Average_[AgeCountry=&#39;Suède&#39;]]).

Les filtres sont des expressions syntaxiques qui font référence à une ou plusieurs dimensions et éléments de dimension. Comme vous l’avez vu dans l’exemple ci-dessus, l’utilisation de l’expression [!DNL [dimension=element]] est un moyen facile de spécifier un filtre.

Il est tout aussi facile d’appliquer un tel filtre pour définir une nouvelle mesure à l’aide d’une expression telle que [!DNL New_Metric=[MetricFilter]]. Un tel filtre peut être utilisé pour définir une nouvelle mesure basée sur un élément de dimension spécifique. Pour utiliser l&#39;exemple ci-dessus, [!DNL Average_[AgeCountry=&#39;Suède&#39;]]spécifie une mesure pour l&#39;âge moyen des personnes en Suède. Si nous devions donner un nom à cette mesure, par exemple l’âge_moyen_suédois, nous pourrions l’utiliser dans d’autres calculs comme mesure. Par exemple, l’évaluation [!DNL Swedish_Average_Age/Average_Age] donnerait un nombre unique : le ratio de l&#39;âge moyen des gens en Suède par rapport à celui des gens dans le reste du monde.

Si le jeu de données contenant des informations sur toutes les personnes dans le monde inclut également une dimension Couleur des yeux, l&#39;expression [!DNL Swedish_Average_[AgeEye_Color=&#39;green&#39;]] résulterait en l&#39;âge moyen des Suédois avec les yeux verts. Vous pouvez également obtenir ce même résultat sans utiliser de définition de mesure intermédiaire en appliquant un filtre différent : [!DNL Average_[AgeCountry=&#39;Suède&#39; ET Eye_Color=&#39;green&#39;]]. Dans ce cas, l’ [!DNL AND] opérateur spécifie une expression de filtre à l’aide de deux autres expressions de filtre de base.
