---
description: Les mesures, dimensions et filtres apportent un cadre dans lequel des calculs sont effectués concernant les données traitées dans un jeu de données Data Workbench.
title: Mesures, dimensions et filtres Data Workbench
uuid: 3c0300a0-ae19-4817-aab8-7294e0eabdd9
exl-id: 687d9695-e70c-49ff-ac11-1537e6309e16
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: ht
source-wordcount: '827'
ht-degree: 100%

---

# Mesures, dimensions et filtres Data Workbench {#data-workbench-metrics-dimensions-and-filters}

Les mesures, dimensions et filtres apportent un cadre dans lequel des calculs sont effectués concernant les données traitées dans un jeu de données Data Workbench.

Les résultats des calculs définis à l’aide de ce cadre sont affichés dans des espaces de travail, des tableaux de bord, des rapports et d’autres sorties. En résumé, tout nombre que vous voyez dans une application ou provenant d’une application est le résultat d’une requête d’un jeu de données qui implique une mesure, une dimension et un filtre.

Au niveau le plus élémentaire, une mesure décrit ce qui est calculé de et sur le jeu de données, une dimension ventile les données du jeu de données en catégories et un filtre décrit une partie ou un sous-ensemble sélectionné de données dans le jeu de données.

Lorsque le serveur Data Workbench traite les données pour créer un jeu de données, les dimensions des données sont créées, puis mises à jour de manière régulière à mesure que les nouvelles données sont lues et traitées par le serveur. Les mesures et les filtres sont calculés à partir de ces dimensions de données.

>[!CAUTION]
>
>Si vous redéfinissez une mesure interne, le système se comportera de manière inattendue en raison de la mauvaise valeur. Vos rapports ne se généreront pas, sauf si une mesure indique 100 %. Nous vous recommandons de ne pas changer les définitions de la mesure.

## Exemple {#section-ecc465d1a5e34d559c1983e96fa409ec}

Imaginez un jeu de données qui contient des informations concernant toutes les personnes dans le monde. Ce jeu de données contient au minimum toutes les personnes dans le monde et leur âge. L’âge moyen serait une mesure utile à calculer dans ce jeu de données. L’évaluation de cette mesure entraînerait un nombre : l’âge moyen de la population mondiale.

Ajouter une dimension au jeu de données rendrait ces informations plus utiles et gérables. Si le jeu de données contient le pays de résidence de chaque personne, définir une dimension Pays apporterait une manière de segmenter les personnes en groupes représentant chaque pays du monde. L’évaluation de la mesure Âge moyen sur la dimension Pays entraînerait une liste de nombres, une pour chaque pays, représentant chacune l’âge moyen des habitants de ce pays.

L’application d’un filtre (ou filtre de sélection) dans une formule de mesures peut donner des informations plus détaillées ou permettre la définition d’une nouvelle mesure en fonction de mesures et de dimensions existantes. L’évaluation de la mesure Âge moyen avec un filtre pour lequel « le pays est égal à Suède » entraîne un nombre : l’âge moyen des habitants de la Suède. L’âge moyen suédois pourrait être une mesure basée sur ce filtre.

Par exemple :

```
Swedish_Average_Age=Average_Age[country = ‘Sweden’]
```

## Relation entre les mesures, les dimensions et les filtres {#section-28622596124140b280e6b993b174ef84}

En général, l’évaluation d’une mesure par rapport à une dimension entraîne l’évaluation d’une mesure pour chaque élément de dimension (ou élément). Dans l’exemple ci-dessus, la dimension Pays possède un élément pour chaque pays du monde. L’évaluation de l’âge moyen par pays produirait l’âge moyen pour chacun des éléments (pays), y compris l’élément Suède.

Il est important de noter que lorsque vous évaluez une mesure par rapport à une dimension, vous recevrez le même résultat numérique pour un élément de dimension spécifique que vous évaluiez la mesure pour la dimension complète ou que vous définissiez un filtre correspondant à cet élément de dimension spécifique. Dans l’exemple précédent, lorsque vous regardez l’âge moyen des habitants de la Suède, l’une ou l’autre des méthodes suivantes donnerait des résultats identiques :

* Évaluer la mesure Âge moyen par rapport à la dimension Pays, puis regarder le nombre pour l’élément de dimension Suède.
* Évaluer la mesure Âge moyen avec un filtre « habitants de la Suède » (exprimé sous la forme [!DNL Average_Age[Country=&#39;Sweden&#39;]]).

Les filtres sont des expressions syntaxiques qui font référence à une ou plusieurs dimensions et éléments de dimension. Comme vous l’avez vu dans l’exemple ci-dessus, l’utilisation de l’expression [!DNL [dimension=element]] est une manière simple d’affiner un filtre.

Appliquer un tel filtre pour définir une nouvelle mesure à l’aide d’une expression comme [!DNL New_Metric=Metric[Filter]] est tout aussi simple. Un tel filtre peut être utilisé pour définir une nouvelle mesure en fonction d’un élément de dimension spécifique. Pour reprendre l’exemple ci-dessus, [!DNL Average_Age[Country=&#39;Sweden&#39;]] précise une mesure pour l’âge moyen des habitants de la Suède. Si nous devions donner un nom à cette mesure, comme Swedish_Average_Age, nous pourrions l’utiliser dans d’autres calculs en tant que mesure. Par exemple, évaluer [!DNL Swedish_Average_Age/Average_Age] entraînerait un nombre unique : le rapport entre l’âge moyen des habitants de la Suède par rapport à celui des habitants dans le reste du monde.

Si le jeu de données contenant les informations tous les habitants du monde incluait également une dimension Couleur des yeux, l’expression [!DNL Swedish_Average_Age[Eye_Color=&#39;green&#39;]] donnerait l’âge moyen des Suédois aux yeux verts. Vous pourriez également obtenir le même résultat sans utiliser une définition de mesure intermédiaire en appliquant un filtre différent : [!DNL Average_Age[Country=&#39;Sweden&#39; AND Eye_Color=&#39;green&#39;]]. Dans ce cas, l’opérateur [!DNL AND] précise une expression de filtre utilisant deux autres expressions de filtre de base.
