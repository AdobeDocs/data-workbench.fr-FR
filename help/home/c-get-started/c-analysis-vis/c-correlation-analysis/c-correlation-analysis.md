---
description: Les corrélations statistiques mesurent des relations significatives pour identifier les opportunités grâce à une exploration avancée des données.
title: Matrice de corrélation
uuid: 7f6bdb65-dc31-4e27-9870-4c9402ee6031
exl-id: 79c23bb9-2b4b-4fe0-bfdb-52721fbbdf0c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 0%

---

# Matrice de corrélation{#correlation-matrix}

Les corrélations statistiques mesurent des relations significatives pour identifier les opportunités grâce à une exploration avancée des données.

En utilisant le [coefficient de corrélation Pearsons](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c), la matrice de corrélation vous fournit des informations pertinentes afin de mieux identifier les étapes suivantes d’une campagne marketing, d’améliorer la conception du site ou de continuer à analyser en profondeur les clients pour les dépendances de corrélation supplémentaires.

## Création d’une matrice de corrélation {#section-87ed12ccc1af4196a1b6534e621c4cbb}

La matrice de corrélation compare les mesures sur une dimension dénombrable ou non dénombrable. La matrice peut ensuite être modifiée afin de mettre en surbrillance les corrélations dans la visualisation par sélection des couleurs ou pour la rendre sous forme de carte textuelle, de carte thermique, ou les deux.

1. Ouvrez une Matrice de corrélation.

   Cliquez avec le bouton droit de la souris [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Correlation Matrix]. Le tableau de dimension s’ouvre.

   ![](assets/correlation_matrix_2.png)

   Sélectionnez une dimension, par exemple [!DNL Time] > [!DNL Day of the Week] dans ce menu. Le tableau de corrélation s’ouvre avec la dimension identifiée dans le coin de la matrice et la mesure associée placée dans la ligne et la colonne. Pour la dimension Jour de la semaine, **[!UICONTROL Visits]** est la mesure associée.

   ![](assets/correlation_matrix_1.png)

   La corrélation est de 1 000 car vous comparez une mesure à elle-même (ce qui reflète une corrélation parfaite, mais inutilisable).

1. Modifiez l’une des mesures.

   Cliquez avec le bouton droit de la souris et sélectionnez **[!UICONTROL Change Metric]** pour modifier une mesure dans la ligne ou la colonne. Cela configure une corrélation entre deux mesures de valeur.

   Pour cet exemple, remplacez la mesure **[!UICONTROL Visits]** de la colonne par **[!UICONTROL Internal Searches]**. Cliquez avec le bouton droit et sélectionnez [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Internal Searches].

   ![](assets/correlation_matrix_change_metric.png)

1. Ajoutez d’autres mesures à la matrice de corrélation.

   Cliquez avec le bouton droit de la souris dans une colonne ou une ligne de mesure. Par exemple, dans le menu Mesure, ajoutez [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Sign in Error].

   ![](assets/correlation_matrix_11.png)

   La nouvelle mesure s’affiche dans une colonne avec un numéro de corrélation. Vous pouvez ajouter d’autres mesures, telles que **[!UICONTROL Email Signups]**, pour créer le tableau.

   ![](assets/correlation_matrix_6.png)

   Vous pouvez également ajouter des mesures aux lignes à comparer aux mesures des colonnes.

   ![](assets/correlation_matrix_add_metric.png)

1. (facultatif) Limitez une mesure en ajoutant un élément de dimension.

   Cliquez avec le bouton droit dans l’espace de travail et sélectionnez **[!UICONTROL Table]**. Dans le tableau de dimension ouvert, appuyez sur Ctrl + Alt et faites glisser l’élément sur une mesure dans une colonne ou une ligne. L’élément s’affiche entre parenthèses en regard de la mesure.

   Par exemple, pour la mesure **[!UICONTROL Visits]**, vous pouvez la contraindre en sélectionnant **[!UICONTROL Country]** comme **[!UICONTROL New Zealand]**.

   ![](assets/correlation_matrix_dim_element.png)

   Notez que lorsque vous sélectionnez un élément de dimension, la corrélation change dans toutes les mesures en fonction de l’élément de dimension sélectionné. Seule la mesure Visite sera limitée à &quot;Nouvelle-Zélande&quot; une fois la fenêtre de dimension fermée.

   >[!NOTE]
   >
   >Si vous modifiez une mesure avec une contrainte de dimension (en cliquant avec le bouton droit de la souris et en sélectionnant **[!UICONTROL Change Metric]**), l’élément de dimension qui limite la mesure est perdu. Vous devrez à nouveau ajouter l’élément de dimension.

1. Créez un [filtre binaire](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-binary-filter.md#concept-24e1daff43c540f69019f236976da31c) pour limiter davantage la mesure. Cliquez avec le bouton droit sur la mesure dans le tableau, puis sélectionnez Filtre binaire dans le menu.

## Objectifs de planification et d’analyse des corrélations {#section-cc322da60b7e417ba29e72b0afeb6f79}

Vous trouverez ci-dessous les objectifs généraux de création d’une matrice de corrélation.

**Identifiez la relation entre deux mesures par rapport à une dimension** spécifiée. Dans cet exemple, le tableau a été créé selon la dimension principale, Jour de la semaine, avec les mesures Visite, Enregistrements par e-mail et Erreurs de connexion par rapport aux événements de mesure Recherches internes, Connexion et Enquête affichée.

**Développer des hypothèses pour cibler l&#39;analyse**. Après avoir exécuté une analyse des corrélations, l’étape suivante consiste à rechercher les dépendances et la corrélation des mesures. Par exemple, comprendre que les recherches internes ont un effet sur les inscriptions aux emails permet de prédire cette relation et de modifier les campagnes marketing ou la conception de navigation sur le site web.

**Identifiez les mesures afin d’inclure des algorithmes** d’exploration de données plus avancés. Dans la plupart des cas, les mesures clés sont identifiées, car elles affectent plusieurs corrélations. Vous pouvez désormais utiliser ces mesures clés et les appliquer à une analyse d’exploration de données supplémentaire pour en savoir plus.

## Notes de mise à jour de la matrice de corrélation {#section-ef3626c665ea468a9ecdad624b4132f5}

**Le filtrage et la sélection sur les éléments de dimension d’un tableau comparent des valeurs** similaires. Par exemple, en utilisant la dimension Jour de la semaine, puis en cliquant sur un élément de cette dimension principale, comme en cliquant sur un jour spécifique dans le tableau de dimension Jour de la semaine , une correspondance est affichée à 100 %, ce qui n’offre aucune corrélation utilisable. Comme la dimension racine était Jour de la semaine, toute sélection dans le tableau de dimension Jour de la semaine modifie la matrice en une corrélation individuelle.

![](assets/correlation_matrix_10.png)

Cependant, la corrélation 1 à 1 (lorsqu’une sélection unique est faite de tous les éléments) n’est définie que le jour en question. Si vous effectuez plusieurs sélections, il ne reste pas nécessairement une corrélation de 1 à 1, et ne produit pas toujours une correspondance de 100 %, indépendamment de la sélection de 1 ou 1 jour ou plus de la semaine.

**Les corrélations statistiques ne sont pas égales au modèle** de données corrélées, qui constitue la référence historique des produits Adobe Analytics. La corrélation statistique dans Data Workbench est basée sur le [modèle de corrélation Pearson](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c).

**Afficher la corrélation dans un graphique de dispersion**. Cliquez avec le bouton droit sur le titre d’un graphique de dispersion et choisissez [!DNL Display Correlation] dans le menu [!DNL Visualization]. La valeur Corrélation s’affiche dans la section supérieure droite du graphique de dispersion.

>[!NOTE]
>
>La matrice Graphique de dispersion et Pearsons affiche &quot;Erreur de calcul&quot; si l’application ne parvient pas à exécuter le calcul de corrélation de Pearsons. Cela est généralement dû à des données insuffisantes, ce qui peut entraîner une tentative de division de l’équation par 0.
