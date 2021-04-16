---
description: Sélectionnez des variables d’entrée, le nombre de grappes et une population de cibles (si vous le souhaitez) pour définir des grappes dans votre jeu de données.
title: Création des clusters
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
exl-id: 60bc75bf-2f89-455b-8be9-aa20bb837752
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 1%

---

# Création des clusters{#building-clusters}

Sélectionnez des variables d’entrée, le nombre de grappes et une population de cibles (si vous le souhaitez) pour définir des grappes dans votre jeu de données.

**Création des clusters**

1. Ouvrez le **[!UICONTROL Cluster Builder]**.

   Cliquez sur **Visualisation** > **Analyses prédictives** > **Mise en grappe** > **Créateur de clusters**.

   ![](assets/cluster-builder-step1.png)

1. Sélectionnez des variables d’entrée.

   * Ajoutez les mesures à la liste **[!UICONTROL Input Variables]** en les sélectionnant dans le menu **[!UICONTROL Metric]** de la barre d&#39;outils.

      ![](assets/cluster_metric_select.png)

   * Ajoutez des éléments de dimension à la liste **[!UICONTROL Input Variables]** en les faisant glisser depuis une table de Dimension.

      Appuyez sur **[!UICONTROL Ctrl + Alt]** et faites glisser les éléments de dimension sélectionnés vers la liste **[!UICONTROL Input Variables]** ou vers la zone **[!UICONTROL Element]** de la barre d’outils.

      ![](assets/cluster_dim_select.png)
   Par défaut, la mise en grappe est effectuée sur l’ensemble du jeu de données. Vous pouvez afficher toutes les variables d&#39;entrée dans le volet de gauche **[!UICONTROL Preprocessing]**.
1. Utilisez le menu **[!UICONTROL Options]** pour sélectionner le nombre de grappes souhaité.

   ![](assets/build_cluster_2.png)

1. Si vous souhaitez regrouper un sous-ensemble de Visiteurs dans votre jeu de données, vous pouvez définir un filtre de population.

   ![](assets/build_cluster_3.png)

   Début en définissant le sous-ensemble souhaité à l’aide de sélections dans votre espace de travail ou en utilisant **[!UICONTROL Filter Editor]**. Une fois que vous avez sélectionné le sous-ensemble de votre choix, définissez la Cible Population dans le menu **[!UICONTROL Options]**. Il est recommandé de donner un nom d’identification au groupe ciblé.

   Le menu **[!UICONTROL Options]** comporte également des paramètres permettant de contrôler le nombre maximal de passes et le seuil acceptable de convergence centrale.

1. Une fois les entrées et les options configurées, cliquez sur le bouton **Aller** pour exécuter la mise en grappe localement ou appuyez sur **[!UICONTROL Submit]** pour envoyer la tâche au serveur Predictive Analytics Server. Les envois au serveur enregistrent la dimension résultante dans le jeu de données une fois la convergence terminée.

   Lors d’une exécution locale, le Cluster Builder passe par quatre étapes de mise en grappe de la canopée, dans la mesure où il définit des centres intelligents en fonction des entrées.

   Une fois que les centres des grappes cessent de changer plus que le seuil de convergence spécifié, la Dimension de cluster est convergée et le Générateur de grappes affiche des informations supplémentaires sur la pertinence d’une entrée pour chaque grappe.

1. Personnalisez les grappes.

   Cliquez avec le bouton droit sur la barre de couleurs des statistiques pour ouvrir un menu contextuel vous permettant de personnaliser les seuils de pertinence et, dans le cas des distributions d’éléments de dimension, de choisir le test qui s’affiche.

   ![](assets/build_cluster_7.png)

   Les entrées de mesure fournissent un test en t pour chaque grappe, tandis que les entrées d’éléments de dimension fournissent trois tests de distribution (Chi au carré, une statistique U d’entropie et la statistique V de Cramer) pour chaque grappe.

   >[!NOTE]
   >
   >Si vous ajoutez ou supprimez des entrées au cours de la convergence, le processus s’interrompt jusqu’à ce que vous appuyiez de nouveau sur **Go**.

   Après avoir créé des grappes, vous pouvez ouvrir le sélecteur de couleurs pour attribuer des couleurs à différents résultats de distribution.

   ![](assets/build_cluster_5.png)

1. Une fois la Dimension de cluster convergée, vous pouvez ajouter des mesures au tableau et effectuer des sélections normalement. Vous pouvez également cliquer avec le bouton droit de la souris sur les noms d’éléments (Cluster 1, Cluster 2, etc.) pour ouvrir le menu contextuel afin de les renommer en un élément plus significatif.

   ![](assets/build_cluster_6.png)

1. Si vous souhaitez utiliser cette dimension de grappe dans d’autres visualisations, vous pouvez la **[!UICONTROL Save]** localement ou la **[!UICONTROL Submit]** au serveur.

Si vous souhaitez réexécuter la convergence ou voir la pertinence des entrées, Cluster Builder peut également charger les dimensions de grappe existantes.

>[!TIP]
>
>Si cette option est sélectionnée, **[!UICONTROL Reset]** libère complètement toutes les variables d’entrée et vous offre une visualisation vide du créateur de grappes pour définir de nouvelles grappes.
