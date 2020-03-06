---
description: Sélectionnez des variables d’entrée, le nombre de grappes et une population cible (le cas échéant) pour définir des grappes dans votre jeu de données.
solution: Analytics
title: Création de grappes
topic: Data workbench
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Création de grappes{#building-clusters}

Sélectionnez des variables d’entrée, le nombre de grappes et une population cible (le cas échéant) pour définir des grappes dans votre jeu de données.

**Création de grappes**

1. Ouvrez le **[!UICONTROL Cluster Builder]**.

   Cliquez sur **Visualisation** > Analyses **** prédictives > **Mise en grappe** > Créateur de **grappes.**

   ![](assets/cluster-builder-step1.png)

1. Sélectionnez des variables d’entrée.

   * Ajoutez des mesures à la **[!UICONTROL Input Variables]** liste en les sélectionnant dans le **[!UICONTROL Metric]** menu de la barre d’outils.

      ![](assets/cluster_metric_select.png)

   * Ajoutez des éléments de dimension à la **[!UICONTROL Input Variables]** liste en les faisant glisser du tableau d’une dimension.

      Appuyez **[!UICONTROL Ctrl + Alt]** et faites glisser les éléments de dimension sélectionnés vers la **[!UICONTROL Input Variables]** liste ou la **[!UICONTROL Element]** zone de la barre d’outils.

      ![](assets/cluster_dim_select.png)
   Par défaut, la mise en grappe est effectuée sur l’ensemble du jeu de données. Vous pouvez afficher toutes les variables d’entrée dans le volet de gauche **[!UICONTROL Preprocessing]** .
1. Utilisez le **[!UICONTROL Options]** menu pour sélectionner le nombre de grappes souhaité.

   ![](assets/build_cluster_2.png)

1. Si vous souhaitez regrouper un sous-ensemble des visiteurs dans votre jeu de données, vous pouvez définir un filtre de population.

   ![](assets/build_cluster_3.png)

   Commencez par définir le sous-ensemble souhaité à l’aide des sélections dans votre espace de travail ou en utilisant le **[!UICONTROL Filter Editor]**. Une fois que le sous-ensemble souhaité est sélectionné, définissez la population cible dans le **[!UICONTROL Options]** menu. Il est recommandé de donner au groupe ciblé un nom d’identification.

   Le **[!UICONTROL Options]** menu comporte également des paramètres permettant de contrôler le nombre maximal de passes et le seuil acceptable de convergence centrale.

1. Une fois les entrées et les options configurées, cliquez sur le bouton **Valider** pour exécuter la mise en grappe localement ou appuyez **[!UICONTROL Submit]** sur pour envoyer la tâche au serveur d’analyses prédictives. Les envois au serveur enregistrent la dimension résultante dans le jeu de données une fois la convergence terminée.

   Lors de l’exécution locale, le Créateur de grappes de serveurs passe par quatre étapes de mise en grappe de la canopée, dans la mesure où il définit des centres intelligents en fonction des entrées.

   Une fois que les centres des grappes cessent de changer plus que le seuil de convergence spécifié, la dimension de cluster est convergée et le créateur de grappes affiche des informations supplémentaires sur la pertinence d’une entrée pour chaque grappe.

1. Personnalisez les grappes.

   Un clic droit sur la barre de couleurs des statistiques ouvre un menu contextuel qui vous permet de personnaliser les seuils de pertinence et, dans le cas des distributions d’éléments de dimension, de choisir le test qui s’affiche.

   ![](assets/build_cluster_7.png)

   Les entrées de mesure fournissent un test en t pour chaque grappe, tandis que les entrées d’éléments de dimension fournissent trois tests de distribution (le carré Chi, une statistique U d’entropie et la statistique V de Cramer) pour chaque grappe.

   >[!NOTE]
   >
   >Si vous ajoutez ou supprimez des entrées pendant la convergence, le processus s’interrompt jusqu’à ce que vous activiez de nouveau **OK** .

   Après avoir créé des grappes, vous pouvez ouvrir le sélecteur de couleurs pour attribuer des couleurs à différents résultats de distribution.

   ![](assets/build_cluster_5.png)

1. Une fois la dimension de cluster convergée, vous pouvez ajouter des mesures au tableau et effectuer des sélections normalement. Vous pouvez également cliquer avec le bouton droit de la souris sur les noms d’éléments (Grappe 1, Grappe 2, etc.) pour ouvrir le menu contextuel afin de les renommer en élément plus significatif.

   ![](assets/build_cluster_6.png)

1. Si vous souhaitez utiliser cette dimension de grappe dans d’autres visualisations, vous pouvez **[!UICONTROL Save]** l’utiliser localement ou **[!UICONTROL Submit]** sur le serveur.

Si vous souhaitez réexécuter la convergence ou voir la pertinence des entrées, Cluster Builder peut également charger des dimensions de grappe existantes.

>[!TIP]
>
>Lorsque cette option est sélectionnée, **[!UICONTROL Reset]** toutes les variables d’entrée sont libérées et vous pouvez visualiser le créateur de grappes vide pour définir de nouvelles grappes.

