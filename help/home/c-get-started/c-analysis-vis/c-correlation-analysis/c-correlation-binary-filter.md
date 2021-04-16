---
description: Un filtre binaire dans la matrice de corrélation vous permet de limiter les valeurs d’une des mesures corrélées ou des deux pour mieux cibler la comparaison.
title: Filtre binaire dans la matrice de corrélation
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
exl-id: e693fc72-5697-4c47-a498-e0d4d875c688
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 5%

---

# Filtre binaire dans la matrice de corrélation{#binary-filter-in-the-correlation-matrix}

Un filtre binaire dans la matrice de corrélation vous permet de limiter les valeurs d’une des mesures corrélées ou des deux pour mieux cibler la comparaison.

Pour définir un filtre binaire sur une matrice de corrélation :

1. Dans la matrice de corrélation, cliquez avec le bouton droit de la souris sur un nom de mesure.
1. Sélectionnez **Modifier les détails de la mesure**.

   ![](assets/correlation_matrix_binary_filter.png)

   La fenêtre **[!UICONTROL Edit Correlation Metric Details]** s&#39;ouvre.

   ![](assets/correlation_matrix_metric_details.png)

1. Configurez un filtre binaire.

   Cliquez d’abord sur le paramètre **[!UICONTROL Inactive]**. Il bascule pour définir le filtre sur **[!UICONTROL Active]** et affiche les champs **Comparaison** et **Valeur**.

   Sélectionnez ensuite un opérateur **[!UICONTROL Comparison]** et définissez son **[!UICONTROL Value]** pour configurer un filtre pour la mesure sélectionnée.

>[!IMPORTANT]
>
>Le filtre binaire pour le Data Workbench 6.2 a été mis à jour avec de nouvelles fonctionnalités, ce qui nécessite de recréer toute matrice de corrélation avec un filtre binaire créé dans les versions précédentes.

## Ajouter les éléments de Dimension {#section-f19f4e0368ca488e92d1e28bcc24417c}

Vous pouvez également ajouter un élément de dimension pour limiter une mesure. Une mesure ne peut être associée qu’à un seul élément.

![](assets/correlation_matrix_element.png)

Cliquez avec le bouton droit dans l&#39;espace de travail et sélectionnez **Tableau**. Ouvrez une dimension avec ses éléments et faites-la glisser vers le paramètre **[!UICONTROL Element]** de la fenêtre Modifier les détails de la mesure de corrélation ou déposez une mesure dans la matrice de corrélation.
