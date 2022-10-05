---
description: Toutes les données que vous souhaitez exporter doivent être définies comme une dimension dans le profil.
title: Créer des dimensions à utiliser avec l’exportation de segments
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
exl-id: 0f16c242-10f6-4014-b848-ea001e9d085c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 8%

---

# Créer des dimensions à utiliser avec l’exportation de segments{#create-dimensions-for-use-with-segment-export}

{{eol}}

Toutes les données que vous souhaitez exporter doivent être définies comme une dimension dans le profil.

Si la dimension n’existe pas déjà dans le profil, vous devez la créer. Vous pouvez créer des dimensions à l’aide de l’une des méthodes suivantes :

* Ajoutez une dimension à la variable [!DNL Transformation.cfg] fichier . Voir *Guide de configuration des jeux de données*.

* Créer [!DNL .dim] fichier . Voir [Création et modification de Dimensions dérivées](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

* Effectuez des sélections dans une visualisation telle qu’une cartographie des processus ou un segment et enregistrez les sélections en tant que dimension. Voir [Enregistrement de Dimensions à partir de mappages de processus](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) et [Création de Dimensions de segment](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e).

L’exportation d’un champ de données tel que l’ID de suivi ou l’adresse électronique (qui peut contenir de nombreux éléments) nécessite de créer une dimension Denormal qui stocke les chaînes brutes de données.

Pour plus d’informations sur les dimensions non normalisées, voir *Guide de configuration des jeux de données*.
