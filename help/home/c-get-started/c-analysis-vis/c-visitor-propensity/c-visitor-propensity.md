---
description: Le score de propension vous permet de définir des clients en fonction de leur possibilité d’une conversion réussie ou de l’achèvement d’un événement spécifié. Il vous permet d’optimiser l’impact potentiel des efforts avant d’exécuter un processus ou de diriger une campagne.
title: Score de propension
uuid: 4f7163f5-6fe4-4f87-9e27-71ec8b4717af
exl-id: 832a1e6c-8eeb-4dcc-97e8-9570e1a6eb4f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 24%

---

# Score de propension{#propensity-scoring}

Le score de propension vous permet de définir des clients en fonction de leur possibilité d’une conversion réussie ou de l’achèvement d’un événement spécifié. Il vous permet d’optimiser l’impact potentiel des efforts avant d’exécuter un processus ou de diriger une campagne.

## Avantages du score de propension   {#section-c51ece66effc42de9b754f0f46027c1b}

Le score de propension vous permet d’effectuer une découverte de données afin d’identifier les comportements masqués ou les modèles qui existent dans vos données. Le score de propension permet tout particulièrement d’identifier des groupes de clients similaires à l’aide de méthodes plus objectives et ciblées que la segmentation ou le filtrage. En outre, le score de propension permet de configurer des fonctionnalités de prédiction pour identifier le comportement des clients à forte valeur ajoutée de votre entreprise.

Une fois l’audience à forte valeur ajoutée identifiée, vous pouvez entrer en contact avec elle. Par exemple, si vous êtes Business to Business, vous pouvez avoir des pistes d’appels de vente qui vous permettent ensuite de noter les pistes et d’identifier leur probabilité de conversion hors ligne. Dans la mesure où chaque prospect augmente les coûts, la création d’une offre spéciale qui permet d’identifier les clients pour lesquels la probabilité de conversion est la plus élevée est plus efficace et plus rentable en ce qui concerne l’affectation de vos ressources.

Le score de propension aide à identifier les facteurs qui permettent le plus de prévoir un score spécifique ou d’augmenter la probabilité qu’un événement ait lieu. Il permet aussi de répondre à des questions spécifiques : Le client fera-t-il l’objet d’une conversion ? Le client répondra-t-il à un e-mail ? Le client effectuera-t-il un nouvel achat ? Le score de propension vous permet de répondre à ces questions et d’identifier les visiteurs ayant tendance à passer à l’action qui peuvent être configurés et comptabilisés.

En outre, vous pouvez utiliser des filtres pour définir un sous-ensemble de visiteurs à noter à l’aide de la fonction facultative **[!UICONTROL Training Filter]**. Si aucun filtre n’est appliqué, tous les visiteurs sont ciblés pour la notation.

## Fonctionnalités de la visualisation du score de propension {#section-28413bc7d33b42c59cecb427c1c5a3fa}

Pour ouvrir la visualisation du score de propension, cliquez sur **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

![](assets/propensity_visualization_GO.png)

La visualisation du score de propension comprend les fonctionnalités suivantes, accessibles à partir de sa barre d’outils :

| Fonctionnalité Barre d’outils | Description |
|---|---|
| Valider | Cliquez sur pour exécuter le processus de notation après avoir configuré les paramètres. |
| Réinitialiser le | Effacez tous les paramètres de la visualisation. |
| Load | Charge un ScoreDim créé précédemment qui vous permet de modifier et/ou de recréer le modèle de notation. |
| Enregistrer | Enregistrez la visualisation Score de propension sous forme de fichier Dim pour y accéder et l’ouvrir si nécessaire. |
| Submit | Tâche d’envoi de notation pour le traitement côté serveur. |
| Options | Définissez le filtre d’entraînement pour limiter le sous-ensemble de visiteurs. Le filtre par défaut est **[!UICONTROL Train on Everyone]**, mais vous pouvez le modifier en effectuant des sélections dans l’espace de travail ou en créant un filtre à l’aide de **[!UICONTROL Filter Editor]**. |
| Définir Target | Définissez la variable dépendante. |
| Mesure | Ajout de mesures en tant que variables indépendantes. |
| éléments ; | Faites glisser des éléments de Dimension à l’aide des clés `<Ctrl>` + `<Alt>` des tables de Dimension. |

**Voir également**:

* Les [Graphiques Gain et Effet élévateur](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a). Ces vues peuvent être ouvertes à partir d’un modèle de notation complet ou à partir de [!DNL Add Visualization> Predictive Analytics > Scoring.]
* [Visionneuse de modèles](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-d4fdf4b335c04b0ea07e70ab9a7ce9dd). Ces vues peuvent être ouvertes à partir d’un modèle de notation complet ou à partir de [!DNL Add Visualization> Predictive Analytics > Scoring.]
* [Description complexe du filtre](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-complex-filter.md#concept-f9c55e54837f4b5995a00bc950ce5dff).

## Utilisation de la visualisation du score de propension {#section-63ced03fa2eb44f2b8a98d61a6c88122}

* **Définissez un ou plusieurs filtres afin de définir la population de visiteurs pour la notation**. Cette option **[!UICONTROL Training Filter]** vous permet de cibler les visiteurs selon des critères sélectionnés. Si aucun filtre de formation n’est appliqué, tous les visiteurs sont ciblés pour la notation. Si le filtre d’entraînement est défini, le résultat de la notation est significatif pour la population de visiteurs définie, bien que chaque visiteur reçoive toujours un score.
* **Identifier les visiteurs** positifs. Pour définir la variable dépendante afin de spécifier un filtre cible identifiant les visiteurs positifs qui correspondent au résultat souhaité. Cela peut être aussi simple que Recettes > 10 $ ou un filtre beaucoup plus complexe.
* **Le filtre Cible n’est pas autorisé comme le filtre** Formation . En toute logique, le filtre cible doit être un ajout au filtre d’entraînement, ce qui entraîne la notation d’un sous-ensemble positif de la population de visiteurs.
* **Sélectionnez des variables d’intérêt (variables indépendantes) en tant qu’entrées dans l’algorithme** de score de propension. Il peut s’agir de mesures ou d’éléments individuels d’une Dimension. Le score de propension démarre le prétraitement comme dans la [clusterisation de visiteur](../../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d). Le système commence à capturer un certain nombre d’échantillons correspondant à la définition du filtre d’entraînement précédemment défini (le cas échéant). Actuellement, la taille de l’échantillon est définie sur 10 % de la population d’évaluation (définie par un filtre de formation), avec un minimum de 20 000 et un maximum de 100 000, et est liée à la taille de la population d’évaluation.

* Une Dimension de score se compose d’éléments compris entre 0 % et 100 % qui déterminent la probabilité que les visiteurs correspondent à la variable Target.
