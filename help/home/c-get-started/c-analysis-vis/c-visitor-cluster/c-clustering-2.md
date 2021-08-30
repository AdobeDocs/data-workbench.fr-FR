---
description: Le Créateur de clusters comprend désormais un algorithme KMeans++ (seul l’algorithme KMeans était auparavant pris en charge) qui utilise une approche plus rapide pour rechercher des centres pour un processus de génération de clusters accéléré.
title: Clusterisation 2.0
uuid: 14462bd3-06d1-4622-a2d8-f96aadb357f3
exl-id: 6a779ddc-c8f1-4c55-9c17-1119fe1aa791
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Clusterisation 2.0{#clustering}

Le Créateur de clusters comprend désormais un algorithme KMeans++ (seul l’algorithme KMeans était auparavant pris en charge) qui utilise une approche plus rapide pour rechercher des centres pour un processus de génération de clusters accéléré.

## Algorithmes KMeans {#section-92383a1be1d6402c95a25c902e90b850}

Dans [Cluster Builder](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/visitor-cluster/c-visitor-cluster.html?lang=en), vous pouvez désormais sélectionner **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** pour sélectionner des algorithmes lors de la définition de grappes.

* **[!UICONTROL KMeans]**. Cet algorithme utilise la mise en grappe de canopées pour définir les centres de la grappe.
* **[!UICONTROL KMeans++]**. Cet algorithme accélère la création de grappes lors de l’exécution sur de grands ensembles de données.

<!-- <a id="section_8193A6D60C5540BB985085BE670B4544"></a> -->

KMeans++ est une mise en oeuvre améliorée de l’algorithme de mise en grappe KMeans, car il fournit une meilleure initialisation des centres k initiaux. (L’algorithme KMeans d’origine choisit les centres initiaux de manière aléatoire.) KMeans++ sélectionne aléatoirement le premier centre. Les autres centres k-1 seront choisis un par un en fonction de la distance d’un point de données par rapport au centre existant le plus proche. Les points de données les plus éloignés ont une meilleure chance d’être choisis comme nouveau centre que les points de données avoisinants. Une fois le centre initial sélectionné, la procédure est exécutée exactement de la même manière que la mise en grappe KMeans d’origine.

Le workflow pour KMeans++ est exactement le même que celui de la mise en grappe des KMeans, sauf que vous devez sélectionner **Options** > **Algorithme** > **KMeans++** dans le créateur de grappe.

>[!NOTE]
>
>Chaque unité de traitement applique sa propre procédure KMeans++ sur sa propre partie de données. Si le DPU dispose de suffisamment de mémoire disponible (le ratio est configurable dans le fichier PAServer.cfg), les données des variables impliquées seront alors transférées dans la mémoire. Le reste de la sélection centrale initiale et des itérations convergentes k-1 se produisent dans la mémoire, ce qui est plus rapide que la mise en grappe précédente de KMeans.
