---
description: Les données que vous souhaitez exporter doivent être définies comme une dimension dans le profil.
solution: Analytics
title: Création de dimensions à utiliser avec l’exportation de segments
topic: Data workbench
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Création de dimensions à utiliser avec l’exportation de segments{#create-dimensions-for-use-with-segment-export}

Les données que vous souhaitez exporter doivent être définies comme une dimension dans le profil.

Si la dimension n’existe pas déjà dans le profil, vous devez la créer. Vous pouvez créer des dimensions à l’aide de l’une des méthodes suivantes :

* Ajoutez une dimension au [!DNL Transformation.cfg] fichier. Voir le Guide *de configuration des jeux de* données.

* Créez un nouveau [!DNL .dim] fichier. Voir [Création et modification de dimensions](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93)dérivées.

* Effectuez des sélections dans une visualisation telle qu’un mappage de processus ou un segment et enregistrez les sélections sous forme de dimension. Voir [Enregistrement de dimensions à partir de zones](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) de processus et [Création de dimensions](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e)de segment.

L’exportation d’un champ de données, tel que l’ID de suivi ou l’adresse électronique (qui peut comporter un grand nombre d’éléments) nécessite la création d’une dimension Denormal qui stocke les chaînes brutes de données.

Pour plus d’informations sur les dimensions Denormal, voir le Guide *de configuration des jeux de* données.
