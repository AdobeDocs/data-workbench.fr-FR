---
description: Une visionneuse de modèles vous permet de générer un modèle de régression logistique à l’aide de la fonction Score de propension.
solution: Analytics
title: Visionneuse de modèles
topic: Data workbench
uuid: 7ee8ff29-21c2-4721-804a-c7a5d101b50b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Model Viewer{#model-viewer}

Une visionneuse de modèles vous permet de générer un modèle de régression logistique à l’aide de la fonction Score de propension.

La visionneuse de modèles affiche les pondérations des coefficients de chaque variable d’entrée (y compris le terme constant) et leur plage d’erreurs statistiques. Les variables d&#39;entrée présentant un coefficient absolu élevé et une faible marge d&#39;erreur sont les plus importants prédicteurs du modèle.

**Pour ouvrir un graphique de la visionneuse de modèles**

1. Select [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Passez la souris sur Modèle terminé d’un score enregistré.

![](assets/propensity_model_viewer.png)

Les variables d&#39;entrée avec un coefficient >= 1 sont des influences positives sur le modèle de propension. Les coefficients &lt; 1 sont des influences négatives sur le modèle de propension. La plage définie entre parenthèses est l’erreur et indique la cohérence de la variable d’entrée dans la population qui a réussi.
