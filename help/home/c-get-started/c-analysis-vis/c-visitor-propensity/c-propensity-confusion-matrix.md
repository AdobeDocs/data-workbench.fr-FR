---
description: Les calculs statistiques pour le score de propension sont définis.
solution: Analytics
title: Calcul du score de propension
topic: Data workbench
uuid: 67270864-0468-4cc9-b48b-0e880f813555
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Calcul du score de propension{#calculating-propensity-scoring}

Les calculs statistiques pour le score de propension sont définis.

Sur le plan conceptuel, le score calculé pour chaque visiteur est une probabilité estimée que l’événement spécifié (défini par le filtre cible) puisse se produire, ce qui donne une plage de valeurs de score comprise entre 0 et 100 %. La procédure de notation utilise des échantillons existants comme données de formation pour trouver la relation entre la probabilité d’événement et les variables indépendantes sélectionnées présentant un intérêt.

Mathématiquement, ces relations se reflètent dans chaque valeur quantitative associée à chaque variable indépendante. Ces valeurs sont appelées coefficients de modèle. ScoreDim utilise actuellement l’algorithme IRLS (itérativement repondéré les moindres carrés) pour estimer les coefficients du modèle. IRLS passe en revue les échantillons à plusieurs reprises jusqu&#39;à ce que la différence de coefficients entre la passe actuelle et la passe précédente soit inférieure à 1,0e-6, auquel moment on l&#39;appelle **convergé**. Cependant, selon les données, l&#39;IRLS peut ne pas être en mesure d&#39;atteindre la convergence.

Dans ce cas, l’itération de formation du modèle se termine lorsque

* la différence de coefficient devient plus grande au lieu de plus petite,
* 1 000 laissez-passer ont été atteints, ou
* une erreur mathématique empêche la poursuite de l’itération.

Si IRLS ne converge pas, un algorithme de sauvegarde appelé Stochastic Gradient Decent (SGD) sera utilisé. La SGD examinera également les exemples de formation à plusieurs reprises. Mais contrairement à l&#39;IRLS, les coefficients du modèle SGD sont contrôlés de sorte que la différence entre les itérations diminuera toujours de manière exponentielle. De même, la SGD prendra fin lorsque la différence de coefficient sera inférieure à 1,0e-6 ou 100 000 passes ont été atteintes. L&#39;échec de l&#39;IRLS et l&#39;engagement de la SGD seront enregistrés dans le journal de trace.

Pour les deux algorithmes, tous les exemples ne sont pas inclus dans la formation des modèles. 80 % sont actuellement utilisés pour former le modèle. Une fois le modèle formé, les 20 p. 100 restants seront utilisés pour évaluer l&#39;intensité du modèle en termes d&#39;exactitude, de rappel et de précision, qui est calculé à partir de la matrice de confusion. Plus près de 100 %, plus le modèle de score est efficace.
