---
description: Un filtre binaire dans la matrice de corrélation vous permet de limiter les valeurs d’une des mesures corrélées ou des deux pour mieux cibler la comparaison.
solution: Analytics
title: Filtre binaire dans la matrice de corrélation
topic: Data workbench
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Filtre binaire dans la matrice de corrélation{#binary-filter-in-the-correlation-matrix}

Un filtre binaire dans la matrice de corrélation vous permet de limiter les valeurs d’une des mesures corrélées ou des deux pour mieux cibler la comparaison.

Pour définir un filtre binaire sur une matrice de corrélation :

1. Dans la matrice de corrélation, cliquez avec le bouton droit de la souris sur un nom de mesure.
1. Sélectionnez **Modifier les détails** de la mesure.

   ![](assets/correlation_matrix_binary_filter.png)

   La **[!UICONTROL Edit Correlation Metric Details]** fenêtre s&#39;ouvrira.

   ![](assets/correlation_matrix_metric_details.png)

1. Configurez un filtre binaire.

   Cliquez d’abord sur le **[!UICONTROL Inactive]** paramètre. Il bascule pour définir le filtre comme **[!UICONTROL Active]** et affiche les champs **Comparaison** et **Valeur** .

   Sélectionnez ensuite un **[!UICONTROL Comparison]** opérateur et définissez-le **[!UICONTROL Value]** pour configurer un filtre pour la mesure sélectionnée.

>[!IMPORTANT]
>
>Le filtre binaire pour les outils de données version 6.2 a été mis à jour avec de nouvelles fonctionnalités, ce qui nécessite de recréer toute matrice de corrélation avec un filtre binaire créé dans les versions précédentes.

## Ajout d’éléments de dimension {#section-f19f4e0368ca488e92d1e28bcc24417c}

Vous pouvez également ajouter un élément de dimension pour limiter une mesure. Une mesure ne peut être associée qu’à un seul élément.

![](assets/correlation_matrix_element.png)

Cliquez avec le bouton droit de la souris dans l’espace de travail et sélectionnez **Tableau**. Ouvrez une dimension avec ses éléments et faites-la glisser vers le **[!UICONTROL Element]** paramètre de la fenêtre Modifier les détails de la mesure de corrélation ou déposez une mesure dans la matrice de corrélation.
