---
description: Une visionneuse de modèles vous permet de générer un modèle de régression logistique à l’aide de la fonction Score de propension.
title: Visionneuse de modèles
uuid: 7ee8ff29-21c2-4721-804a-c7a5d101b50b
exl-id: e0e4acd4-76a2-436a-993b-2bb7ca91ae1a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 3%

---

# Visionneuse de modèles{#model-viewer}

Une visionneuse de modèles vous permet de générer un modèle de régression logistique à l’aide de la fonction Score de propension.

La visionneuse de modèles affiche les poids de coefficients de chaque variable d&#39;entrée (y compris le terme constant) et leur plage d&#39;erreurs statistiques. Les variables d&#39;entrée présentant un coefficient absolu élevé et une faible marge d&#39;erreur sont les prédicteurs les plus significatifs du modèle.

**Pour ouvrir un graphique de la visionneuse de modèles**

1. Sélectionnez [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. Passez la souris sur Modèle terminé pour afficher un score enregistré.

![](assets/propensity_model_viewer.png)

Les variables d&#39;entrée avec un coefficient >= 1 sont des influences positives sur le modèle de propension. Les coefficients &lt; 1 sont des influences négatives sur le modèle de propension. La plage définie entre parenthèses est l’erreur et indique la cohérence de la variable d’entrée dans la population qui a réussi.
