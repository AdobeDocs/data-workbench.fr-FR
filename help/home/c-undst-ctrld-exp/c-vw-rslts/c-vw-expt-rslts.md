---
description: Après avoir ajouté le nouveau champ au fichier Log Processing.cfg et créé la nouvelle transformation Split et la dimension étendue, vous pouvez vue la nouvelle dimension étendue que vous avez créée dès que l’étape de saisie rapide du retraitement des données est terminée.
solution: Analytics,Analytics
title: Affichage des résultats de l’expérience
topic: Data workbench
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---


# Affichage des résultats de l’expérience{#viewing-the-experiment-results}

Après avoir ajouté le nouveau champ au fichier Log Processing.cfg et créé la nouvelle transformation Split et la dimension étendue, vous pouvez vue la nouvelle dimension étendue que vous avez créée dès que l’étape de saisie rapide du retraitement des données est terminée.

Par défaut, cette dimension affiche le nombre de sessions pour chacun de vos groupes d’expériences.

**Pour vue de la dimension expérimentale**

* Dans n’importe quel espace de travail de [!DNL Insight], ouvrez un tableau avec la dimension expérimentale que vous avez créée.

   Les éléments de dimension de l’expérience, qui représentent chaque expérience en cours et chaque groupe dans chaque expérience, s’affichent avec le nombre actuel de sessions pour chaque groupe. Chaque groupe est nommé au format suivant en utilisant le nom de l’expérience suivi du nom du groupe :

   *Nom de l’expérience.Nom du groupe*

   Par exemple : [!DNL New Homepage.Control]

Le tableau suivant présente la dimension Groupes d’expériences contrôlées qui a été créée dans [!DNL Transformation.cfg] et chacune des expériences et leurs groupes.

L&#39;expérience Nouvelle page d&#39;accueil est présentée au bas du tableau avec ses deux groupes : Contrôle et index2.

![](assets/controlledexpgrps.png)

Vous pouvez désormais utiliser la dimension de l’expérience et toute mesure pertinente pour explorer et interpréter les résultats de l’expérience, ainsi que créer des rapports utiles détaillant ces résultats.
