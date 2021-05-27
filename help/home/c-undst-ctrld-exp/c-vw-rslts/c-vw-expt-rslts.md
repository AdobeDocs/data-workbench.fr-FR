---
description: Après avoir ajouté le nouveau champ au fichier Log Processing.cfg et créé la nouvelle transformation Partage et la dimension étendue, vous pouvez afficher la nouvelle dimension étendue que vous avez créée dès que l’étape d’entrée rapide du retraitement des données est terminée.
solution: Analytics,Analytics
title: Affichage des résultats de l’expérience
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
exl-id: cada693c-79cb-4f49-a2f0-6ff60425be1c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---

# Affichage des résultats de l’expérience{#viewing-the-experiment-results}

Après avoir ajouté le nouveau champ au fichier Log Processing.cfg et créé la nouvelle transformation Partage et la dimension étendue, vous pouvez afficher la nouvelle dimension étendue que vous avez créée dès que l’étape d’entrée rapide du retraitement des données est terminée.

Cette dimension, par défaut, affiche le nombre de sessions pour chacun de vos groupes d’expériences.

**Pour afficher la dimension de l’expérience**

* Dans n’importe quel espace de travail de [!DNL Insight], ouvrez un tableau avec la dimension d’expérience que vous avez créée.

   Les éléments de dimension de l’expérience, qui représentent chaque expérience que vous exécutez et chaque groupe au sein de chaque expérience, s’affichent avec le nombre actuel de sessions pour chaque groupe. Chaque groupe est nommé au format suivant à l’aide du nom de l’expérience suivi du nom du groupe :

   *Nom de l’expérience.Nom du groupe*

   Par exemple : [!DNL New Homepage.Control]

Le tableau suivant présente la dimension Groupes d’expériences contrôlées qui a été créée dans [!DNL Transformation.cfg] et chacune des expériences et de leurs groupes.

L&#39;expérience New Homepage est présentée au bas du tableau avec ses deux groupes : Contrôle et index2.

![](assets/controlledexpgrps.png)

Vous pouvez désormais utiliser la dimension de l’expérience et toutes les mesures pertinentes pour explorer et interpréter les résultats de l’expérience, ainsi que créer des rapports utiles détaillant ces résultats.
