---
description: Les graphiques Effet élévateur et Gain présentent des visualisations d’offre pour évaluer les performances potentielles d’un modèle noté afin d’évaluer les performances sur des portions définies de l’audience.
title: Gain de propension et courbes d’élévation
uuid: 4f08277e-deea-48d3-ab15-214c43ad6664
exl-id: 5ac08512-ac9c-4e85-a4f9-ea6d819095d8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 1%

---

# Gain de propension et courbes d’élévation{#propensity-gain-and-lift-charts}

Les graphiques Effet élévateur et Gain présentent des visualisations d’offre pour évaluer les performances potentielles d’un modèle noté afin d’évaluer les performances sur des portions définies de l’audience.

Les graphiques de gain et d’effet élévateur sont des visualisations créées pour évaluer les performances potentielles du modèle marqué. Ces graphiques évaluent le rendement de chaque portion de la population.

**Pour ouvrir un graphique à effet élévateur ou à gain**

1. Sélectionnez [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Passez la souris sur **[!UICONTROL Model Complete]** d’un score enregistré.

![](assets/propensity_lift_gain_1.png)

**A propos des diagrammes d&#39;effet élévateur et de gain**

Les graphiques d’effet élévateur et de gain constituent des outils visuels utiles pour mesurer la valeur d’un modèle prédictif. Les deux graphiques sont constitués d&#39;une courbe d&#39;effet élévateur (verte) et d&#39;une ligne de base (rose). Pour le **diagramme de gain**, la distance entre la courbe d&#39;effet élévateur et la ligne de base représente la mesure dans laquelle vous pouvez améliorer les performances des réponses (ou le &quot;gain&quot;) à partir du mode prédictif. Le gain est réalisé en hiérarchisant et en ciblant les prospects (clients/visiteurs) les plus susceptibles de se convertir, plutôt que de les commercialiser aléatoirement auprès des clients/visiteurs. Ainsi, vous pouvez quantifier la valeur attendue de l’utilisation du modèle prédictif pour choisir les prospects à contacter.

Comme pour le diagramme des gains, le **diagramme des effets élévateurs** montre combien vous êtes plus susceptible de recevoir des réponses positives que si vous avez contacté des prospects au hasard. Vous souhaitez que la distance entre la courbe d’effet élévateur et la ligne de base soit aussi grande que possible, ce qui représente des gains attendus plus importants de l’utilisation du modèle prédictif pour contacter les clients. Mathématiquement, les graphiques de gain et d&#39;effet élévateur sont définis comme suit :

* **Gain** = (Réponse attendue à l’aide d’un modèle prédictif pour contacter les Prospects) / (Réponse attendue des Prospects à contact aléatoire)
* **Effet élévateur** = (Réponse attendue d&#39;un groupe spécifique Taille des Prospects identifiées à l&#39;aide du modèle prédictif) / (Réponse attendue d&#39;un groupe spécifique Taille des Prospects identifiées de façon aléatoire)

**Exemple de graphiques d’effet élévateur et de gain**

Prenons l’exemple d’un détaillant qui souhaite lancer une campagne de marketing de relance par courriel pour vendre un pantalon de yoga. Historiquement, l’analyste s’attend à un taux de réponse moyen de 20 % en fonction des campagnes de marketing de relance par courriel précédentes semblables à celle-ci. Bien que l&#39;analyste compte près de 5 millions de clients dans sa base de données de messagerie, l&#39;entreprise ne souhaite commercialiser que les clients les plus susceptibles de répondre aux courriels et aux achats. De cette manière, la société optimise le RSI de la campagne tout en s’assurant qu’elle n’envoie pas inutilement de courriers électroniques à des clients inintéressés. Compte tenu d’un taux de réponse attendu de 20 %, le spécialiste du marketing et l’analyste s’attendent à ce qu’environ 1 million de clients répondent et achètent. Plutôt que de deviner de manière aléatoire quels clients seront parmi les 20 % de réponses, l&#39;analyste veut être intelligent pour prédire lequel des un million de prospects (sur la base de données de 5 millions de clients) est le plus susceptible de répondre.

Grâce à la fonctionnalité de score d&#39;Audience de l&#39;Adobe, l&#39;analyste définit la réussite comme un clic de prospect sur un courriel et un pantalon de yoga acheté (la variable dépendante). Après avoir sélectionné les variables indépendantes (en fonction de l’expérience et des connaissances acquises lors de l’analyse des corrélations des données et de la mise en grappe des audiences entre d’autres analyses), chaque prospect est notée sur la probabilité de répondre positivement à la campagne de marketing de relance par courriel (en cliquant sur le courriel et en achetant un pantalon de yoga). L’analyste ouvre les graphiques Gain et Effet élévateur résultants en fonction du modèle prédictif.

L’axe y montre le pourcentage des réponses positives cumulées attendues. Dans notre exemple, nous prévoyons un total de 1 million de réponses positives. Une valeur de 20 % sur l&#39;axe des ordonnées correspond à 20 % des 1 million de réponses positives attendues, soit 200 000 réponses positives. L’axe X montre le pourcentage de clients potentiels contactés. Dans notre exemple, l&#39;axe X représente une fraction des 5 millions de clients dans la base de données des courriels. La ligne de base (rose) est le taux de réponse global. Si vous contactez X % des prospects, vous recevrez X % des réponses positives totales. En utilisant le modèle prédictif, la courbe d&#39;effet élévateur (verte) montre le pourcentage de réponses positives obtenues (axe y) en contactant un pourcentage donné de prospects (axe x).

Le graphique Effet élévateur trace l’effet élévateur attendu résultant de l’utilisation du modèle prédictif pour déterminer le million de prospects les plus susceptibles d’acheter un pantalon de yoga après avoir reçu et cliqué sur le courriel. Pour contacter 20 % des prospects sélectionnées de manière aléatoire sans modèle prédictif, vous devez vous attendre à recevoir 20 % des répondants. Cependant, en utilisant le modèle prédictif pour identifier les 20 % de prospects les plus susceptibles de répondre, vous vous attendez à obtenir 50 % des répondants. La valeur y de la courbe d&#39;effet élévateur à 20 % est de 50/20 = 2,5. Le graphique d&#39;effet élévateur montre combien vous êtes plus susceptible de recevoir des répondants que si vous contactez un échantillon aléatoire de prospects. Par exemple, en contactant seulement 20 % des prospects en fonction du modèle prédictif, vous atteindrez 2,5 fois plus de répondants que si vous n&#39;avez utilisé aucun modèle prédictif.
