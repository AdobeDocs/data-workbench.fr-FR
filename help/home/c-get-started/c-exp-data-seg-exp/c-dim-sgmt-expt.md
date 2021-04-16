---
description: Les données que vous souhaitez exporter doivent être définies comme une dimension dans le profil.
title: Créer des dimensions à utiliser avec l’exportation de segments
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
exl-id: 0f16c242-10f6-4014-b848-ea001e9d085c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 8%

---

# Créer des dimensions à utiliser avec l’exportation de segments{#create-dimensions-for-use-with-segment-export}

Les données que vous souhaitez exporter doivent être définies comme une dimension dans le profil.

Si la dimension n’existe pas déjà dans le profil, vous devez la créer. Vous pouvez créer des dimensions à l’aide de l’une des méthodes suivantes :

* Ajoutez une dimension au fichier [!DNL Transformation.cfg]. Consultez le *Guide de configuration des jeux de données*.

* Créez un nouveau fichier [!DNL .dim]. Voir [Création et modification de Dimensions dérivées](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

* Effectuez des sélections dans une visualisation telle qu’un mappage de processus ou un segment et enregistrez les sélections sous forme de dimension. Voir [Enregistrement de Dimensions à partir de Process Maps](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) et [Création de Dimensions de segment](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e).

L’exportation d’un champ de données tel que l’ID de suivi ou l’adresse électronique (qui peut contenir de nombreux éléments) nécessite la création d’une dimension Denormal qui stocke les chaînes brutes de données.

Pour plus d&#39;informations sur les dimensions Denormal, consultez le *Guide de configuration des ensembles de données*.
