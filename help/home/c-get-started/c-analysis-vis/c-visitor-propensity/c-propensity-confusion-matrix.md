---
description: Les calculs statistiques pour le score de propension sont définis.
title: Calcul du score de propension
uuid: 67270864-0468-4cc9-b48b-0e880f813555
exl-id: 679e1363-fd10-4a44-a85a-ef0daefaf303
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 1%

---

# Calcul du score de propension{#calculating-propensity-scoring}

{{eol}}

Les calculs statistiques pour le score de propension sont définis.

Conceptuellement, le score calculé pour chaque visiteur est une probabilité estimée que l’événement spécifié (défini par le filtre cible) se produise, ce qui se traduit par une plage de valeurs de score comprise entre 0 et 100 %. La procédure de notation utilise des exemples existants comme données de formation pour trouver la relation entre la probabilité d’événement et les variables d’intérêt indépendantes sélectionnées.

Mathématiquement, ces relations se reflètent dans chaque valeur quantitative associée à chaque variable indépendante. Ces valeurs sont appelées des coefficients de modèle. ScoreDim utilise actuellement l’algorithme des moindres carrés (IRLS), sous forme itérative, pour estimer les coefficients du modèle. IRLS passe en revue les échantillons plusieurs fois jusqu’à ce que la différence de coefficient entre le passage actuel et le passage précédent soit inférieure à 1,0e-6, ce qui l’appelle **convergé**. Cependant, selon les données, l&#39;IRLS peut ne pas parvenir à la convergence.

Dans ce cas, l’itération de formation du modèle se termine lorsque

* la différence de coefficient devient plus grande au lieu de plus petite,
* 1 000 laissez-passer ont été atteints, ou
* une erreur mathématique empêche la poursuite de l’itération.

Si l’IRLS ne converge pas, un algorithme de sauvegarde appelé Déformation du dégradé stochastique (SGD) est utilisé. Le SGD va également passer plusieurs fois en revue les échantillons d&#39;entraînement. Mais contrairement à IRLS, les coefficients du modèle SGD sont contrôlés de sorte que la différence entre les itérations diminuera toujours de manière exponentielle. De même, la SGD prendra fin lorsque la différence de coefficient sera inférieure à 1,0e-6 ou 100 000 passes ont été atteintes. L&#39;échec de l&#39;IRLS et l&#39;engagement de la SGD seront enregistrés dans le log de trace.

Pour les deux algorithmes, tous les exemples n’entrent pas dans la formation de modèle. 80 % sont actuellement utilisés pour entraîner le modèle. Une fois le modèle formé, les 20 % restants seront utilisés pour évaluer la force du modèle en termes de précision, de rappel et de précision, calculés à partir de la matrice de confusion. Plus près de 100 %, plus le modèle de notation est efficace.
