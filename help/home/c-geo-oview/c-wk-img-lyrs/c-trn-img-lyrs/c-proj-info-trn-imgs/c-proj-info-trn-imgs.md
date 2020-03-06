---
description: La géographie des outils de données prend en charge les projections latitude-longitude et les projections UTM (Universal Transverse Mercator) pour toutes les sources de couches d’images du terrain.
solution: Analytics
title: Spécification des informations de projection pour les images de terrain
topic: Data workbench
uuid: 4a476192-e749-4187-b64e-9794f39b0019
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Spécification des informations de projection pour les images de terrain{#specifying-projection-information-for-terrain-images}

La géographie des outils de données prend en charge les projections latitude-longitude et les projections UTM (Universal Transverse Mercator) pour toutes les sources de couches d’images du terrain.

Les informations de projection sont requises pour les bitmaps bruts non projetés et les images générales, non projetées. Vous pouvez spécifier des informations de projection pour les images avec des informations de projection incorporées, même si elles ne sont généralement pas requises car les paramètres de la projection sont déterminés automatiquement à partir de données géodésiques incorporées dans l’image elle-même. Les sections suivantes fournissent des détails sur la spécification de ces formats de projection dans le [!DNL Terrain Images.cfg] fichier.
