---
description: La mise en grappe des visiteurs vous permet d’exploiter les caractéristiques des clients afin de classer dynamiquement les visiteurs et de générer des ensembles de clusters en fonction d’entrées de données sélectionnées, afin d’identifier les groupes ayant des intérêts et des comportements similaires pour l’analyse et le ciblage des clients.
title: Clusterisation de visiteur
uuid: 0c16aaa0-1d86-43a6-a7e2-b43b3ea80dc5
exl-id: 68c1845d-9c49-4ad9-adf3-c123d08cf758
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 2%

---

# Clusterisation de visiteur{#visitor-clustering}

La mise en grappe des visiteurs vous permet d’exploiter les caractéristiques des clients afin de classer dynamiquement les visiteurs et de générer des ensembles de clusters en fonction d’entrées de données sélectionnées, afin d’identifier les groupes ayant des intérêts et des comportements similaires pour l’analyse et le ciblage des clients.

**Processus de mise en grappe**

Le processus de mise en grappe nécessite l’identification des mesures et des éléments de dimension à utiliser comme entrées et vous permet de choisir une population cible spécifique à laquelle appliquer ces éléments pour créer des grappes spécifiées. Lorsque vous exécutez le processus de mise en grappe, le système utilise les entrées de mesure et de dimension pour déterminer les centres initiaux appropriés pour le nombre spécifié de grappes. Ces centres sont ensuite utilisés comme point de départ pour appliquer l’algorithme K-Means.

![](assets/K_algorithm.png)

* Les premiers centres sont choisis intelligemment via un col de clustering avec canopy.
* Les grappes de données sont créées en associant chaque point de données au centre le plus proche.
* La moyenne de chacun des groupes de K devient le nouveau centre.
* L’algorithme est répété aux étapes 2 et 3 jusqu’à ce que la convergence soit atteinte. Cela peut prendre plusieurs passes.

**[!UICONTROL Maximum Iterations]** dans le menu **[!UICONTROL Options]** permet à l’analyste de spécifier le nombre maximal d’itérations à effectuer par l’algorithme de mise en grappe. Si vous définissez cette option, le processus de mise en grappe peut être plus rapide en fonction du plafond d’itérations maximal, au détriment de la convergence exacte des centres de la grappe.

>[!NOTE]
>
>Une fois les clusters définis, la Dimension de clusters peut être enregistrée pour être utilisée comme toute autre dimension. Il peut également être chargé dans l’Explorateur de clusters pour examiner la séparation des centres de clusters.

Dans le Créateur de clusters, vous pouvez sélectionner **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** pour sélectionner des algorithmes lors de la définition de clusters. Actuellement, 3 algorithmes sont pris en charge :

* KMeans
* Kmean`++`
* Optimisation des attentes

Il existe deux façons d’exécuter le processus de mise en grappe :

* Méthode 1 : cliquez sur **[!UICONTROL Go]** dans la fenêtre de visualisation du cluster.
* Méthode 2 : cliquez sur **[!UICONTROL Submit]** dans la fenêtre de visualisation du cluster, qui envoie directement la tâche de mise en grappe au serveur. Vous pouvez suivre la progression par le biais de l’option &quot;Statut détaillé de la requête&quot;.

![](assets/dwb_visitorclustering.png)

L’algorithme présente les restrictions suivantes :

1. Si vous utilisez la méthode 1, vous pouvez sélectionner l’un des algorithmes de mise en grappe pris en charge.
1. Si vous utilisez la méthode 2, vous pouvez sélectionner les clés ou les clés++. L’option Maximisation de l’attente n’est pas disponible.

>[!NOTE]
>
>Dans le fichier [!DNL DPU.cfg], la valeur de &#39;Requête, Limite de mémoire&#39; est définie sur 500 Mo par défaut. Cette valeur doit être augmentée lors de l’exécution de plusieurs tâches de mise en grappe. Par exemple, si vous exécutez 5 tâches de mise en grappe en parallèle, augmentez cette valeur à 1 Go. Il n’existe aucun moyen d’annuler la tâche de mise en grappe sans redémarrer le serveur.

**Recommandations**

Le nombre d’itérations (nombre de fois où les données sont analysées) et le seuil de convergence que vous configurez affectent grossièrement les performances de la mise en grappe. Le tableau suivant fournit une ligne directrice plus large que vous pouvez suivre :

| Nombre de clusters | Algorithme | Itérations | Seuil de convergence | Normalisation |
|---|---|---|---|---|
| 6 | Keans | 25 500 | 1e-3 | Min. max. |
| 6 | Keans | 25 500 | 1e-6 | Min. max. |
| 6 | Keans++ | 50 | 1e-6 | Min. max. |
