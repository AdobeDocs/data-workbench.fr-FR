---
description: Configurez un arbre de décision en identifiant un cas positif et en ajoutant des entrées de mesure et de dimension pour évaluer les données et explorer l’arbre de décision.
title: Création d’un arbre de décision
uuid: 5790d322-5460-444d-95d8-a06696f9a55f
exl-id: 06db9e77-72ea-44c7-8451-d3f195acd196
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 0%

---

# Création d’un arbre de décision{#building-a-decision-tree}

{{eol}}

Configurez un arbre de décision en identifiant un cas positif et en ajoutant des entrées de mesure et de dimension pour évaluer les données et explorer l’arbre de décision.

Pour créer une arborescence de décision, procédez comme suit.

1. Ouvrez un nouvel espace de travail.

   Après avoir ouvert un nouvel espace de travail, vous devrez peut-être cliquer sur **Ajouter** > **Déverrouillage temporaire**.

1. Pour ouvrir le créateur d’arbre de décision, cliquez avec le bouton droit de la souris **[!UICONTROL Visualization]** > **Analyses prédictives** > **Classification** > **Créateur d’arbre de décision**.

1. Définir une **Cas positif**.

   Vous pouvez définir un cas positif pour une arborescence de décision en sélectionnant des dimensions dans un Finder ou des éléments de dimension dans un tableau, ou en concevant un filtre dans le filtre de conception. En fait, le cas positif peut être une combinaison de plusieurs sélections dans l’espace de travail, y compris des filtres, des dimensions, des éléments et tous les types de valeurs de visualisation de Data Workbench.

   * **Conception et application d’un filtre** comme un cas positif. Cliquez avec le bouton droit dans l’espace de travail et sélectionnez **[!UICONTROL Tools]** > **[!UICONTROL Filter Editor]** pour concevoir et appliquer un filtre.

   * Ajouter **Dimensions** comme un cas positif. Dans l’espace de travail, cliquez avec le bouton droit de la souris et sélectionnez **Outils** > **Finders** (ou sélectionnez **[!UICONTROL Add]** > **[!UICONTROL Finders]** dans le volet de gauche). Saisissez un nom de dimension dans la variable **Rechercher** puis sélectionnez une dimension.

   * Ajouter **Mesures** comme un cas positif. Cliquez avec le bouton droit et sélectionnez **Outils** > **Finders** ou sélectionnez **[!UICONTROL Add]** > **[!UICONTROL Finders]** dans le volet de gauche pour ouvrir un tableau Mesures . Sélectionnez une mesure comme cas positif.

   * Ajouter **Éléments de Dimension** comme un cas positif. Cliquez avec le bouton droit dans l’espace de travail et sélectionnez **[!UICONTROL Table]** pour ouvrir des éléments de dimension, sélectionnez l’un des éléments de dimension afin de définir votre casse positive.

1. Cliquez sur **[!UICONTROL Options]** > **[!UICONTROL Set Positive Case]**.

   La casse positive est ainsi définie et vous pouvez la nommer. Le nom apparaît sous le **[!UICONTROL Positive Case]** dans l’espace de travail.

   >[!NOTE]
   >
   >Lorsque vous définissez le cas positif, l’arbre de décision utilise la sélection de l’espace de travail actuel, qui peut être définie comme Visiteurs (ou tout autre compte à rebours de niveau supérieur défini, mais dans la plupart des cas Visiteurs) correspondant à la sélection actuelle dans l’espace de travail. Ils se combinent en un seul filtre pour un seul cas positif (et non plusieurs cas positifs).

   Cliquer **[!UICONTROL Set Positive Case]** si aucune sélection n’est effectuée, le cas positif est effacé.

1. (facultatif) Sélectionnez **[!UICONTROL Set Population Filters]** pour définir la population de visiteurs à classifier.

   Si aucun filtre de population n’est appliqué, le jeu de formations est tiré de tous les visiteurs (la valeur par défaut est &quot;Tout le monde&quot;).

   >[!NOTE]
   >
   >Cliquez sur le bouton **[!UICONTROL Show Complex Filter Description]** pour afficher les scripts de filtrage pour les filtres Cas positif et Population.

1. Ajouter **Mesures**, **Dimensions**, et **Éléments de Dimension** comme entrées.

   Vous pouvez sélectionner des entrées en les faisant glisser et en les déposant dans les panneaux de l’outil de recherche ou dans les tableaux pour des éléments de dimension individuels. Vous pouvez également sélectionner l’option **[!UICONTROL Metrics]** dans la barre d’outils.

   * Ajouter **Mesures** comme entrées.

      Sélectionnez Mesures dans la barre d’outils. Press **Ctrl** + **Alt** pour faire glisser une ou plusieurs mesures vers le créateur d’arbre de décision.

      La mesure apparaît dans la variable **Liste d’entrée (mesures)** comme entrée avec un code couleur unique.

      ![](assets/decision_tree_add_Metrics_inputs.png)

   * Ajouter **Dimensions** comme entrées.

      Dans l’espace de travail, cliquez avec le bouton droit de la souris et sélectionnez **Outils** > **Finder** et saisissez le nom de la dimension dans le champ **Rechercher** champ . Press **Ctrl** + **Alt**, sélectionnez une dimension et faites-la glisser vers le créateur d’arbre de décision.

      La dimension apparaît dans la variable **Entrée (Dimensions)** liste avec un code couleur unique.

   * Ajouter **Éléments de Dimension** comme entrées.

      Dans l&#39;espace de travail, cliquez avec le bouton droit de la souris et sélectionnez un tableau de Dimension. Sélectionnez Éléments de Dimension, puis appuyez sur **Ctrl** + **Alt**, puis faites glisser les éléments sélectionnés vers le créateur d’arbre de décision.

      Les éléments de dimension apparaissent dans la variable **Entrée (éléments)** liste avec un code couleur unique.
   >[!IMPORTANT]
   >
   >Vous pouvez sélectionner jusqu’à quatorze entrées à évaluer. Un message d’erreur s’affiche si trop d’entrées sont ajoutées.

1. Sélectionner **[!UICONTROL Go]** dans la barre d’outils.

   L’arborescence de décision repose sur les dimensions et les mesures sélectionnées. Les mesures simples telles que les ajouts au panier se créent rapidement, tandis que les dimensions complexes telles que la durée de visite avec plusieurs points de données se créent plus lentement avec un pourcentage d’achèvement affiché lors de la conversion. L’arborescence s’actualise et s’ouvre pour une interaction de l’utilisateur. Les entrées de dimension et de mesure seront codées par couleur, conformément aux noms des noeuds.

   ![](assets/decision_tree_builder.png)

   Le noeud terminal s’affiche en vert (true) ou rouge (false) si l’arbre a été élagué et si une prévision de **True** ou **False** suivant les branches élaguées.

   >[!NOTE]
   >
   >L’exemple d’entraînement est extrait du jeu de données pour que le créateur d’arborescence l’utilise. Data Workbench utilise 80 % de l’échantillon pour construire l’arbre et les 20 % restants pour évaluer l’exactitude du modèle de l’arbre.

1. Vérifiez la précision à l’aide de la fonction **[!UICONTROL Confusion Matrix]**.

   Cliquez sur **[!UICONTROL Options]** > **[!UICONTROL Confusion Matrix]** pour afficher les valeurs Précision, Rappel, Précision et F-Score. Plus on se rapproche de 100%, plus le score est élevé.

   La matrice de confusion donne quatre valeurs d’exactitude du modèle en utilisant une combinaison de valeurs :

   * Positif réel (AP)
   * Prédit positif (PP)
   * Négatif réel (AN)
   * Prédit négatif (PN)

   >[!TIP]
   >
   >Ces chiffres sont obtenus en appliquant le modèle de notation obtenu des données de test de 20 % ignorées et déjà connues comme la vraie réponse. Si le score est supérieur à 50 %, il est prédit comme un cas positif (correspondant au filtre défini). Ensuite, Précision = (TP + TN)/(TP + FP + TN + FN), Rappel = TP / (TP + FN) et Précision = TP / (TP + FP).

1. **Exploration de l’arborescence de décision**.

   Après avoir généré une arborescence de décision, vous pouvez afficher le chemin de la prédiction et identifier tous les visiteurs qui répondent aux critères définis. L’arborescence identifie la division d’entrée pour chaque branche en fonction de sa position et de son code couleur. Par exemple, si vous sélectionnez le noeud Domaine référent , les noeuds menant à cette division sont répertoriés par code-couleur à gauche de l’arborescence.

   Vous pouvez effectuer des sélections des noeuds terminaux pour sélectionner des branches (ensembles de règles) de l’arborescence de décision.

   Pour cet exemple : Si la durée de la visite est inférieure à 1, aucune campagne n’existe, au moins une page vue existe, aucune inscription par e-mail et au moins une visite a eu lieu. Les projections sur ces critères de réunion et la commande sont les suivantes : **94,73** pour cent.

   ![](assets/decision_tree_explore.png)

   **Interaction de l’arbre de décision**: Vous pouvez sélectionner plusieurs noeuds dans l’arborescence à l’aide de la méthode standard **Ctrl+clic** pour ajouter ou **Maj+clic** à supprimer.

   **Noeuds codés en couleur**: La couleur des noeuds correspond à la couleur des dimensions et mesures d’entrée, telle qu’elle est affectée par Data Workbench.

   Les noeuds vert et rouge clairs au niveau des feuilles d’une branche élaguée prédisent le noeud comme True ou False.

   | ![](assets/decision_tree_node_true.png) Vert clair | Identifie que le noeud est égal à true et que toutes les conditions sont remplies. |
   |---|---|
   | ![](assets/decision_tree_node_false.png) Bright red | Identifie que le noeud est égal à false et que toutes les conditions ne sont pas remplies. |

1. **Enregistrement de l’arbre de décision**.

   Vous pouvez enregistrer l’arbre de décision dans différents formats :

   ![](assets/decison_tree_save.png)

   * Langage de balisage prédictif (**PMML**), un format de fichier XML utilisé par les applications pour décrire et échanger des modèles d’arbre de décision.
   * **Texte** affichant des colonnes et des lignes simples de vrai ou faux, des pourcentages, du nombre de membres et des valeurs d’entrée.
   * A **Dimension** avec des branches correspondant aux éléments de résultat prévus.
