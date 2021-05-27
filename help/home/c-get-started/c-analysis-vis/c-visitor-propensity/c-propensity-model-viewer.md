---
description: Une visionneuse de modèles vous permet de générer un modèle de régression logistique à l’aide de la fonction Score de propension .
title: Visionneuse de modèles
uuid: 7ee8ff29-21c2-4721-804a-c7a5d101b50b
exl-id: e0e4acd4-76a2-436a-993b-2bb7ca91ae1a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 3%

---

# Visionneuse de modèles{#model-viewer}

Une visionneuse de modèles vous permet de générer un modèle de régression logistique à l’aide de la fonction Score de propension .

La visionneuse de modèles affiche le coefficient de poids de chaque variable d’entrée (y compris le terme constant) et leur plage d’erreurs statistiques. Les variables d’entrée présentant un coefficient absolu élevé et une faible marge d’erreur sont les prédicteurs les plus significatifs du modèle.

**Pour ouvrir un graphique de la visionneuse de modèles**

1. Sélectionnez [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Passez la souris sur la fin du modèle d’un score enregistré.

![](assets/propensity_model_viewer.png)

Les variables d’entrée avec un coefficient >= 1 sont des influences positives sur le modèle de propension. Les coefficients &lt; 1 ont une influence négative sur le modèle de propension. La plage définie entre parenthèses est l’erreur et indique la cohérence de la variable d’entrée sur la population réussie.
