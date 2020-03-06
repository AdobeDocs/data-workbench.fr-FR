---
description: Le créateur de grappes comprend désormais un algorithme KMeans++ (seul l’algorithme KMeans était auparavant pris en charge) qui utilise une approche plus rapide pour rechercher des centres pour un processus accéléré de génération de grappes.
title: Mise en grappe 2.0
uuid: 14462bd3-06d1-4622-a2d8-f96aadb357f3
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Mise en grappe 2.0{#clustering}

Le créateur de grappes comprend désormais un algorithme KMeans++ (seul l’algorithme KMeans était auparavant pris en charge) qui utilise une approche plus rapide pour rechercher des centres pour un processus accéléré de génération de grappes.

## Algorithmes KMeans {#section-92383a1be1d6402c95a25c902e90b850}

Dans le créateur [de](https://docs.adobe.com/help/en/data-workbench/using/client/analysis-visualizations/visitor-cluster/c-visitor-cluster.html)grappes, vous pouvez désormais sélectionner **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** pour sélectionner des algorithmes lors de la définition de grappes.

* **[!UICONTROL KMeans]**. Cet algorithme utilise la mise en grappe de canopées pour définir les centres de la grappe.
* **[!UICONTROL KMeans++]**. Cet algorithme accélère la création de grappe lorsqu’il s’exécute sur de grands ensembles de données.

<!-- <a id="section_8193A6D60C5540BB985085BE670B4544"></a> -->

KMeans++ est une implémentation améliorée de l&#39;algorithme de mise en grappe KMeans, car il fournit une meilleure initialisation des centres k initiaux. (L’algorithme KMeans d’origine choisit les centres initiaux de manière aléatoire.) KMeans++ sélectionne le premier centre de manière aléatoire. Les autres centres k-1 seront choisis un par un en fonction de la distance entre un point de données et le centre existant le plus proche. Les points de données les plus éloignés ont une meilleure chance d’être choisis comme nouveau centre que les points de données avoisinants. Une fois le centre initial choisi, la procédure est exécutée exactement de la même manière que la mise en grappe KMeans d&#39;origine.

Le flux de travail pour KMeans++ est exactement le même que celui pour la mise en grappe de KMeans, sauf que vous devez sélectionner **Options** > **Algorithme** > **KMeans++** dans le créateur de grappes.

>[!NOTE]
>
>Chaque DPU exécute sa propre procédure KMeans++ sur sa propre portion de données. Si le DPU dispose de suffisamment de mémoire disponible (le ratio est configurable dans le fichier PAServer.cfg), les données des variables concernées seront alors transférées en mémoire. Le reste de la sélection de centre de k-1 et des itérations convergentes se produisent dans la mémoire, ce qui est plus rapide que la mise en grappe précédente de KMeans.

