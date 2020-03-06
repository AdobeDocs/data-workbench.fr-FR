---
description: Pour faciliter l’utilisation des statistiques, les outils de données fournissent trois mesures statistiques dans la visualisation de l’analyse guidée.
solution: Analytics
title: Mesures statistiques
topic: Data workbench
uuid: a8782cd2-d657-4c04-9c5d-8e0af2a3b76e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mesures statistiques{#statistical-measures}

Pour faciliter l’utilisation des statistiques, les outils de données fournissent trois mesures statistiques dans la visualisation de l’analyse guidée.

>[!NOTE]
>
>Bien que les mathématiques puissent vous aider à vous faire une idée des corrélations dans vos données, le contexte entourant les données doit également être pris en compte.

* **L’espace réservé** Chi est un test de signification statistique qui contrôle l’aspect de la coche dans la visualisation. Mathématiquement, c&#39;est une probabilité que nous puissions rejeter l&#39;hypothèse nulle, qui indique que les différences observées entre les deux groupes peuvent être expliquées par une variation aléatoire. Pratiquement, si la valeur de l&#39;espace réservé est inférieure à 100 %, nous pouvons ignorer la corrélation quelle que soit sa force mesurée (comme décrit dans les sections statistiques U et V ci-après).
* **La statistique** U est une mesure de la force de la corrélation statistique. Mathématiquement, il vient d&#39;une branche des mathématiques appelée théorie de l&#39;information et est étroitement lié au concept d&#39;information mutuelle entre les distributions des deux groupes. Il peut aussi être considéré comme la compressibilité d&#39;un groupe, compte tenu d&#39;un schéma de codage optimal pour l&#39;autre groupe. En pratique, cette mesure fonctionne très bien dans le cas courant d’une dimension avec de nombreux éléments contenant peu de visiteurs. La mesure varie de 0 (faible) à 1 (forte).
* **La statistique** V est aussi une mesure de la force de la corrélation statistique. Mathématiquement, il est lié à la statistique V de Cramer, qui ne diffère que par une étape de normalisation visant à améliorer la symétrie de la mesure par rapport à l’inversion de sélection. En pratique, cette mesure fonctionne raisonnablement bien avec de nombreux types de dimensions et est liée à une mesure statistique couramment utilisée. La mesure varie de 0 (faible) à 1 (forte).

>[!NOTE]
>
>Les statistiques U et V ont été sélectionnées pour se compléter l&#39;une l&#39;autre, les unes pour détecter les types de corrélations auxquelles l&#39;autre ne réagirait pas aussi fortement.

Grâce à cette visualisation, vous pouvez ajouter d’autres visualisations à votre espace de travail afin de mieux comprendre vos données en fonction de la sélection.

L’ [!DNL Site] exemple suivant contient un graphique à barres qui montre les sessions des jours de janvier, février, mars et avril. Notez qu’un jour de janvier est sélectionné.

![](assets/vis_GuidedAnalysis_withVis.png)

La visualisation de l’analyse guidée dans le coin inférieur gauche de l’espace de travail indique que la dimension Numéro de session fournit des informations utiles sur le jour sélectionné.

En examinant le graphique à barres Numéro de session dans le coin inférieur droit de l’espace de travail, vous pouvez constater que les données de la session numéro 2 sont beaucoup plus faibles que le point de repère. Ainsi, nous pouvons conclure que, en pourcentage, moins de deuxième sessions ont eu lieu le jour choisi que d&#39;habitude. Pour afficher un graphique à barres pour l’une des dimensions répertoriées dans la visualisation de l’analyse guidée, il vous suffit de sélectionner la dimension en cliquant dessus avec la souris.
