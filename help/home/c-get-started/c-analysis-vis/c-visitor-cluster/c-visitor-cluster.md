---
description: La mise en grappe des visiteurs vous permet d’exploiter les caractéristiques des clients pour classer dynamiquement les visiteurs et générer des jeux de grappes en fonction des entrées de données sélectionnées, afin d’identifier les groupes ayant des intérêts et des comportements similaires pour l’analyse et le ciblage des clients.
solution: Analytics
title: Clusterisation de visiteur
topic: Data workbench
uuid: 0c16aaa0-1d86-43a6-a7e2-b43b3ea80dc5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Clusterisation de visiteur{#visitor-clustering}

La mise en grappe des visiteurs vous permet d’exploiter les caractéristiques des clients pour classer dynamiquement les visiteurs et générer des jeux de grappes en fonction des entrées de données sélectionnées, afin d’identifier les groupes ayant des intérêts et des comportements similaires pour l’analyse et le ciblage des clients.

**Processus de mise en grappe**

Le processus de mise en grappe vous oblige à identifier les mesures et les éléments de dimension à utiliser comme entrées et vous permet de choisir une population cible spécifique pour appliquer ces éléments à la création de grappes spécifiées. Lorsque vous exécutez le processus de mise en grappe, le système utilise les entrées de mesure et de dimension pour déterminer les centres initiaux appropriés pour le nombre spécifié de grappes. Ces centres sont ensuite utilisés comme point de départ pour appliquer l’algorithme K-Means.

![](assets/K_algorithm.png)

* Les centres initiaux sont choisis intelligemment par le biais d’un pass de mise en grappe Canopy.
* Les grappes de données sont créées en associant chaque point de données au centre le plus proche.
* La moyenne de chacune des grappes de K devient le nouveau centre.
* L’algorithme est répété aux étapes 2 et 3 jusqu’à ce que la convergence soit atteinte. Cela peut prendre plusieurs passes.

Le **[!UICONTROL Maximum Iterations]** menu **[!UICONTROL Options]** permet à l’analyste de spécifier le nombre maximal d’itérations à effectuer par l’algorithme de mise en grappe. La définition de cette option peut accélérer le processus de mise en grappe en fonction du plafond d’itérations maximum au détriment de la convergence exacte des centres de la grappe.

>[!NOTE]
>
>Une fois les grappes définies, la dimension de cluster peut être enregistrée pour une utilisation identique à toute autre dimension. Il peut également être chargé dans l’Explorateur de grappes afin d’examiner la séparation des centres de grappes.

Dans le Créateur de grappes, vous pouvez sélectionner **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** pour sélectionner des algorithmes lors de la définition de grappes. Il existe actuellement 3 algorithmes pris en charge :

* KMeans
* Keans`++`
* Optimisation des attentes

Il existe deux manières d’exécuter le processus de mise en grappe :

* Méthode 1 - Cliquez sur **[!UICONTROL Go]** dans la fenêtre de visualisation de la grappe.
* Méthode 2 - Cliquez sur **[!UICONTROL Submit]** dans la fenêtre de visualisation de la grappe, qui envoie directement la tâche de mise en grappe au serveur. Vous pouvez suivre l&#39;avancement de l&#39;opération via l&#39;option &quot;Etat détaillé de la requête&quot;.

![](assets/dwb_visitorclustering.png)

L’algorithme comporte les restrictions suivantes :

1. Si vous utilisez la méthode 1, vous pouvez sélectionner l’un des algorithmes de mise en grappe pris en charge.
1. Si vous utilisez la méthode 2, vous pouvez sélectionner kmoyens ou kmoyens++. L’option Optimisation des attentes n’est pas disponible.

>[!NOTE]
>
>Dans le [!DNL DPU.cfg] fichier, la valeur de &quot;Requête, limite de mémoire&quot; est définie sur 500 Mo par défaut. Cette valeur doit être augmentée lors de l’exécution de plusieurs tâches de mise en grappe. Par exemple, si vous exécutez 5 tâches de mise en grappe en parallèle, augmentez cette valeur à 1 Go. Il n’existe aucun moyen d’annuler la tâche de mise en grappe sans redémarrer le serveur.

**Recommandations**

Le nombre d’itérations (nombre de fois que les données sont numérisées) et le seuil de convergence que vous configurez ont une incidence négative sur les performances de la mise en grappe. Le tableau suivant fournit des instructions plus générales que vous pouvez suivre :

| Nombre de grappes | Algorithme | Itérations | Seuil de convergence | Normalisation |
|---|---|---|---|---|
| 6 | Keans | 25,50 | 1e-3 | Min-Max |
| 6 | Keans | 25,50 | 1e-6 | Min-Max |
| 6 | Keans++ | 50 | 1e-6 | Min-Max |
