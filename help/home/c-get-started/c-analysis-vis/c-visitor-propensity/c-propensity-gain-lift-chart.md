---
description: Les graphiques Effet élévateur et Gain offrent des visualisations pour évaluer les performances potentielles d’un modèle noté afin d’évaluer les performances sur des portions définies de l’audience.
solution: Analytics
title: Graphiques Gain de propension et Effet élévateur
topic: Data workbench
uuid: 4f08277e-deea-48d3-ab15-214c43ad6664
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Graphiques Gain de propension et Effet élévateur{#propensity-gain-and-lift-charts}

Les graphiques Effet élévateur et Gain offrent des visualisations pour évaluer les performances potentielles d’un modèle noté afin d’évaluer les performances sur des portions définies de l’audience.

Les graphiques de gain et d’effet élévateur sont des visualisations créées pour évaluer les performances potentielles du modèle marqué. Ces graphiques évaluent le rendement de chaque portion de la population.

**Pour ouvrir un graphique Effet élévateur ou Gain**

1. Select [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Passez la souris sur **[!UICONTROL Model Complete]** un score enregistré.

![](assets/propensity_lift_gain_1.png)

**A propos des graphiques Effet élévateur et Gain**

Les graphiques à effet élévateur et à gain constituent des outils visuels utiles pour mesurer la valeur d’un modèle prédictif. Les deux graphiques sont constitués d’une courbe d’effet élévateur (verte) et d’une ligne de base (rose). Pour le diagramme **** de gain, la distance entre la courbe d’effet élévateur et la ligne de base représente la mesure dans laquelle vous pouvez améliorer les performances des réponses (ou le &quot;gain&quot;) à partir du mode prédictif. Le gain est réalisé en définissant des priorités et en ciblant les prospects (clients/visiteurs) les plus susceptibles de convertir, plutôt que de les cibler de manière aléatoire sur les clients/visiteurs. Vous pouvez ainsi quantifier la valeur attendue de l’utilisation du modèle prédictif pour choisir les prospects à contacter.

À l’instar du diagramme des gains, le graphique **à** effet élévateur montre combien vous êtes plus susceptible de recevoir des réponses positives que si vous avez contacté des prospects au hasard. Vous souhaitez que la distance entre la courbe d’effet élévateur et la ligne de base soit aussi grande que possible, ce qui représente des gains attendus plus importants de l’utilisation du modèle prédictif pour contacter les clients. Mathématiquement, les graphiques de gain et d’effet élévateur sont définis comme suit :

* **Gain** = (Réponse attendue à l&#39;aide d&#39;un modèle prédictif pour contacter les prospects) / (Réponse attendue à partir de perspectives de contact aléatoire)
* **Effet élévateur** = (Réponse attendue d&#39;un groupe spécifique de perspectives identifiées à l&#39;aide du modèle prédictif) / (Réponse attendue d&#39;un groupe spécifique de perspectives identifiées de façon aléatoire)

**Exemple de graphiques de croissance et de gain**

Prenons l’exemple d’un détaillant qui souhaite lancer une campagne de marketing de relance par courriel pour vendre un pantalon de yoga. Historiquement, l’analyste s’attend à un taux de réponse moyen de 20 % sur la base des campagnes de remarketing par courriel précédentes semblables à celle-ci. Bien que l&#39;analyste compte près de 5 millions de clients dans sa base de données de courrier électronique, l&#39;entreprise ne souhaite commercialiser que les clients les plus susceptibles de répondre aux courriers électroniques et aux achats. De cette manière, l’entreprise optimisera le retour sur investissement de la campagne tout en s’assurant qu’elle n’envoie pas inutilement des courriers électroniques à des clients indifférents. Compte tenu d’un taux de réponse attendu de 20 %, le spécialiste du marketing et l’analyste s’attendent à ce qu’environ 1 million de clients répondent et achètent. Plutôt que de deviner de manière aléatoire quels clients seront parmi les 20 % de réponses, l&#39;analyste veut être intelligent pour prédire lequel des 1 million de prospects (sur la base de données de 5 millions de clients) est le plus susceptible de répondre.

En utilisant la fonctionnalité de score d’audience d’Adobe, l’analyste définit la réussite comme un clic de prospect sur un courriel et un pantalon de yoga d’achat (la variable dépendante). Après avoir sélectionné les variables indépendantes (en fonction de l’expérience et des connaissances acquises lors de l’analyse des corrélations des données et de la mise en grappe des audiences, entre autres analyses), chaque prospect est évalué en fonction de sa probabilité de répondre positivement à la campagne de marketing de relance par courriel (en cliquant sur le courriel et en achetant un pantalon de yoga). L’analyste ouvre les graphiques Gain et Effet élévateur résultants en fonction du modèle prédictif.

L’axe des ordonnées indique le pourcentage des réponses positives attendues cumulées. Dans notre exemple, nous nous attendons à un total de 1 million de réponses positives. Une valeur de 20 % sur l’axe des ordonnées correspond à 20 % des 1 million de réponses positives attendues, soit 200 000 réponses positives. L’axe X montre le pourcentage de clients potentiels contactés. Dans notre exemple, l’axe X représente une fraction des 5 millions de clients dans la base de données des courriers électroniques. La ligne de base (rose) correspond au taux de réponse global. Si vous contactez X % des prospects, vous recevrez X % des réponses positives totales. En utilisant le modèle prédictif, la courbe d&#39;effet élévateur (verte) montre le pourcentage de réponses positives obtenues (axe des ordonnées) en contactant un pourcentage donné de perspectives (axe des abscisses).

Le graphique Effet élévateur trace l’effet élévateur attendu en raison de l’utilisation du modèle prédictif pour déterminer le million de personnes les plus susceptibles d’acheter un pantalon de yoga après avoir reçu et cliqué sur le courriel. Pour contacter 20 % des prospects sélectionnés de manière aléatoire sans modèle prédictif, vous devez vous attendre à obtenir 20 % des répondants. Cependant, en utilisant le modèle prédictif pour identifier les 20 % supérieurs des prospects les plus susceptibles de répondre, vous vous attendez à obtenir 50 % des répondants. La valeur y de la courbe d&#39;effet élévateur à 20 % est de 50/20 = 2,5. Le graphique de l’effet élévateur montre combien vous êtes plus susceptible de recevoir des participants que si vous contactez un échantillon aléatoire de prospects. Par exemple, en contactant seulement 20 % des prospects sur la base du modèle prédictif, vous atteindrez 2,5 fois plus de répondants que si vous n&#39;aviez pas utilisé de modèle prédictif.
