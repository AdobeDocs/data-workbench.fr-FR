---
description: Les graphiques Effet élévateur et Gain offrent des visualisations pour évaluer les performances potentielles d’un modèle noté afin d’évaluer les performances par rapport à des parties définies de l’audience.
title: Gain de propension et courbes d’élévation
uuid: 4f08277e-deea-48d3-ab15-214c43ad6664
exl-id: 5ac08512-ac9c-4e85-a4f9-ea6d819095d8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 1%

---

# Gain de propension et courbes d’élévation{#propensity-gain-and-lift-charts}

Les graphiques Effet élévateur et Gain offrent des visualisations pour évaluer les performances potentielles d’un modèle noté afin d’évaluer les performances par rapport à des parties définies de l’audience.

Les graphiques de gain et d’effet élévateur sont des visualisations créées pour évaluer les performances potentielles du modèle noté. Ces graphiques évaluent les performances sur chaque portion de la population.

**Pour ouvrir un graphique Effet élévateur ou Gain**

1. Sélectionnez [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Passez la souris sur **[!UICONTROL Model Complete]** d’un score enregistré.

![](assets/propensity_lift_gain_1.png)

**A propos des graphiques Effet élévateur et Gain**

Les diagrammes de croissance et de gain sont des outils visuels utiles pour mesurer la valeur d’un modèle prédictif. Les deux graphiques se composent d’une courbe d’effet élévateur (vert) et d’une ligne de base (rose). Pour le **graphique de gain**, la distance entre la courbe d’effet élévateur et la ligne de base représente la mesure dans laquelle vous pouvez améliorer les performances des réponses (ou le &quot;gain&quot;) à l’aide du mode prédictif. Le gain est obtenu en établissant des priorités et en ciblant les prospects (clients/visiteurs) les plus susceptibles de se convertir, plutôt que de se lancer dans le marketing de manière aléatoire vers les clients/visiteurs. Ainsi, vous pouvez quantifier la valeur attendue de l’utilisation du modèle prédictif pour choisir les prospects à contacter.

Tout comme pour le graphique Gain, le **diagramme Effet élévateur** indique combien vous êtes plus susceptible de recevoir des réponses positives que si vous avez contacté des prospects de manière aléatoire. Vous souhaitez que la distance entre la courbe d’effet élévateur et la ligne de base soit aussi grande que possible, ce qui représente les gains plus importants attendus de l’utilisation du modèle prédictif pour contacter les clients. Mathématiquement, les graphiques de gain et d’effet élévateur sont définis comme suit :

* **Gain** = (Réponse attendue à l’aide d’un modèle prédictif pour contacter les prospects) / (Réponse attendue à partir de prospects avec contact aléatoire)
* **Effet élévateur**  = (Réponse attendue parmi une taille de groupe spécifique des projets identifiés à l’aide du modèle prédictif) / (Réponse attendue parmi la même taille de groupe spécifique des projets identifiés de manière aléatoire)

**Exemple de graphiques Effet élévateur et Gain**

Prenons l’exemple d’un détaillant qui souhaite lancer une campagne de remarketing par e-mail pour vendre des pantalons de yoga. Historiquement, l’analyste table sur un taux de réponse moyen de 20 % basé sur des campagnes de remarketing par e-mail antérieures similaires à celle-ci. Bien que l’analyste dispose de près de 5 millions de clients dans sa base de données de messagerie, l’entreprise souhaite uniquement commercialiser les clients les plus susceptibles de répondre aux courriers électroniques et aux achats. Ainsi, l’entreprise optimise le retour sur investissement de la campagne tout en s’assurant qu’elle n’envoie pas inutilement d’emails à des clients inintéressés. Compte tenu d’un taux de réponse attendu de 20 %, le marketeur et l’analyste s’attendent à ce qu’environ 1 million de clients répondent et achètent. Plutôt que de deviner aléatoirement lequel de ces clients sera parmi les 20 % de réponses, l’analyste veut être intelligent sur la prédiction du million de prospects (parmi la base de données de 5 millions de clients) le plus susceptible de répondre.

En utilisant la fonctionnalité de notation d’audience de l’Adobe, l’analyste définit la réussite comme un prospect clique sur un email et achète un pantalon de yoga (la variable dépendante). Après avoir sélectionné les variables indépendantes (en fonction de l’expérience et des connaissances acquises lors de l’analyse des corrélations de données et de la mise en grappe d’audiences parmi d’autres analyses), chaque prospect est noté selon sa probabilité de répondre positivement à la campagne de remarketing par e-mail (en cliquant sur l’email et en achetant un pantalon de yoga). L’analyste ouvre les graphiques Gain et Effet élévateur obtenus en fonction du modèle prédictif.

L’axe des ordonnées affiche le pourcentage des réponses positives cumulées attendues. Dans notre exemple, nous prévoyons un total de 1 million de réponses positives. Une valeur de 20 % sur l’axe Y correspond à 20 % des 1 million de réponses positives attendues, soit 200 000 réponses positives. L’axe X indique le pourcentage de clients potentiels contactés. Dans notre exemple, l’axe X représente une fraction des 5 millions de clients dans la base de données email. La ligne de base (rose) est le taux de réponse global. Si vous contactez X % des prospects, vous recevrez X % du total des réponses positives. À l’aide du modèle prédictif, la courbe d’effet élévateur (en vert) indique le pourcentage de réponses positives obtenues (axe Y) en contactant un pourcentage donné de prospects (axe X).

Le graphique Effet élévateur trace l’effet élévateur attendu suite à l’utilisation du modèle prédictif pour déterminer les 1 million de prospects les plus susceptibles d’acheter des pantalons de yoga après avoir reçu et cliqué sur l’email. Pour contacter 20 % des prospects sélectionnés de manière aléatoire sans modèle prédictif, vous devez vous attendre à recevoir 20 % des réponses. Cependant, en utilisant le modèle prédictif pour identifier les 20 % de prospects les plus susceptibles de répondre, vous prévoyez d’obtenir 50 % des réponses. La valeur y de la courbe d’effet élévateur à 20 % est 50/20 = 2,5. Le graphique de l’effet élévateur indique combien vous êtes plus susceptible de recevoir des répondants que si vous contactez un échantillon aléatoire de prospects. Par exemple, en contactant seulement 20 % des prospects en fonction du modèle prédictif, vous atteindrez 2,5 fois plus de répondants que si vous n&#39;avez utilisé aucun modèle prédictif.
