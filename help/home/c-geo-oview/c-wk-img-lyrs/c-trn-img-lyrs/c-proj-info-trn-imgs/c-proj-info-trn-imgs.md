---
description: Data Workbench Geography prend en charge les projections latitude-longitude et les projections UTM (Universal Transverse Mercator) pour toutes les sources de couche d’image du terrain.
title: Préciser les informations de projection des images du terrain
uuid: 4a476192-e749-4187-b64e-9794f39b0019
exl-id: 400b9b59-f700-4b16-8549-fe93140cad1a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 11%

---

# Préciser les informations de projection des images du terrain{#specifying-projection-information-for-terrain-images}

Data Workbench Geography prend en charge les projections latitude-longitude et les projections UTM (Universal Transverse Mercator) pour toutes les sources de couche d’image du terrain.

Les informations de projection sont requises pour les images bitmap brutes non projetées et les images générales, non projetées. Vous pouvez spécifier des informations de projection pour les images avec des informations de projection incorporées, bien qu’elles ne soient généralement pas nécessaires car les paramètres de projection sont déterminés automatiquement à partir de données géodésiques incorporées dans l’image elle-même. Les sections suivantes fournissent des détails sur la spécification de ces formats de projection dans le fichier [!DNL Terrain Images.cfg].
