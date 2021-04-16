---
description: Les calculs statistiques pour le score de propension sont définis.
title: Calcul du score de propension
uuid: 67270864-0468-4cc9-b48b-0e880f813555
exl-id: 679e1363-fd10-4a44-a85a-ef0daefaf303
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 1%

---

# Calcul du score de propension{#calculating-propensity-scoring}

Les calculs statistiques pour le score de propension sont définis.

Conceptuellement, le score calculé pour chaque visiteur est une probabilité estimée que le événement spécifié (défini par le filtre de cible) se produise, ce qui donne une plage de valeurs de score comprise entre 0 et 100 %. La procédure de notation utilise des échantillons existants comme données de formation pour trouver la relation entre la probabilité du événement et les variables indépendantes sélectionnées présentant un intérêt.

Mathématiquement, ces relations se reflètent dans chaque valeur quantitative associée à chaque variable indépendante. Ces valeurs sont appelées coefficients de modèle. ScoreDim utilise actuellement l’algorithme IRLS (Iterativement Repondéré Minimum Squares) pour estimer les coefficients du modèle. IRLS passe en revue les échantillons à plusieurs reprises jusqu&#39;à ce que la différence de coefficients entre la passe actuelle et la passe précédente soit inférieure à 1.0e-6, à ce moment-là elle est appelée **convergé**. Cependant, selon les données, l&#39;IRLS peut ne pas être en mesure d&#39;atteindre la convergence.

Dans ce cas, l&#39;itération de formation du modèle se terminera lorsque

* la différence de coefficient devient plus importante au lieu de plus petite,
* 1 000 laissez-passer ont été atteints, ou
* une erreur mathématique empêche la poursuite de l&#39;itération.

Si IRLS ne converge pas, un algorithme de sauvegarde appelé Stochastic Gradient Decent (SGD) sera utilisé. La SGD va également passer en revue les exemples de formation à plusieurs reprises. Mais contrairement à IRLS, les coefficients du modèle SGD sont contrôlés de sorte que la différence entre itération diminuera toujours de façon exponentielle. De même, la SGD prendra fin lorsque la différence de coefficient sera inférieure à 1,0e-6 ou 100 000 passes ont été atteintes. L&#39;échec de l&#39;IRLS et l&#39;engagement de la SGD seront enregistrés dans le journal de suivi.

Pour les deux algorithmes, tous les exemples ne sont pas inclus dans la formation de modèles. 80 % sont actuellement utilisés pour former le modèle. Une fois le modèle formé, les 20 p. 100 restants seront utilisés pour évaluer la force du modèle en termes de précision, de rappel et de précision qui est calculée à partir de la matrice de confusion. Plus on se rapproche de 100 %, plus le modèle de score est efficace.
