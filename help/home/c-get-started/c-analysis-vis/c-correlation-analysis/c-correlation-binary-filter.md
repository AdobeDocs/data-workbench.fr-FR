---
description: Un filtre binaire dans la matrice de corrélation vous permet de limiter les valeurs d’une mesure ou des deux mesures corrélées afin de mieux cibler la comparaison.
title: Filtre binaire dans la matrice de corrélation
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
exl-id: e693fc72-5697-4c47-a498-e0d4d875c688
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 5%

---

# Filtre binaire dans la matrice de corrélation{#binary-filter-in-the-correlation-matrix}

{{eol}}

Un filtre binaire dans la matrice de corrélation vous permet de limiter les valeurs d’une mesure ou des deux mesures corrélées afin de mieux cibler la comparaison.

Pour définir un filtre binaire sur une matrice de corrélation :

1. Dans la matrice de corrélation, cliquez avec le bouton droit sur le nom d’une mesure.
1. Sélectionner **Modifier les détails d’une mesure**.

   ![](assets/correlation_matrix_binary_filter.png)

   Le **[!UICONTROL Edit Correlation Metric Details]** s’ouvre.

   ![](assets/correlation_matrix_metric_details.png)

1. Configurez un filtre binaire.

   Tout d’abord, cliquez sur le bouton **[!UICONTROL Inactive]** . Il bascule pour définir le filtre comme **[!UICONTROL Active]** et affichez la variable **Comparaison** et **Valeur** champs.

   Sélectionnez ensuite une **[!UICONTROL Comparison]** et définir ses **[!UICONTROL Value]** pour configurer un filtre pour la mesure sélectionnée.

>[!IMPORTANT]
>
>Le filtre binaire pour Data Workbench 6.2 a été mis à jour avec de nouvelles fonctionnalités, ce qui nécessite de recréer toute matrice de corrélation avec un filtre binaire créé dans les versions précédentes.

## Ajout d’éléments de Dimension {#section-f19f4e0368ca488e92d1e28bcc24417c}

Vous pouvez également ajouter un élément de dimension pour contraindre une mesure. Une mesure ne peut être associée qu’à un seul élément.

![](assets/correlation_matrix_element.png)

Cliquez avec le bouton droit dans l’espace de travail et sélectionnez **Tableau**. Ouvrez une dimension avec ses éléments et faites-la glisser sur l’objet **[!UICONTROL Element]** dans la fenêtre Modifier les détails de la mesure de corrélation ou déposez une mesure dans la matrice de corrélation.
