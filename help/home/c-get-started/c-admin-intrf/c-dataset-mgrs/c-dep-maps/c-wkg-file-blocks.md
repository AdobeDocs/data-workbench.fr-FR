---
description: Lorsque vous affichez les composants de jeux de données sur une carte de dépendance, vous avez la possibilité d'activer l'option d'affichage Inclure les blocs de fichiers.
title: Blocs de fichier
uuid: 079dccba-ef19-4895-90bb-6c56f26e8beb
exl-id: 04b0faf1-a16d-4e46-b790-5fe2023f2ba1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 1%

---

# Blocs de fichier{#file-blocks}

Lorsque vous affichez les composants de jeux de données sur une carte de dépendance, vous avez la possibilité d&#39;activer l&#39;option d&#39;affichage Inclure les blocs de fichiers.

Lorsque cette option est activée, le mappage affiche un noeud bleu unique pour toutes les transformations définies dans un fichier de configuration de jeu de données et un noeud vert unique pour toutes les dimensions étendues définies dans un fichier de configuration de jeu de données. Par exemple, si un fichier [!DNL log processing dataset include] contient les définitions de trois transformations, le mappage affiche un noeud bleu représentant les trois transformations. De même, si un fichier [!DNL transformation dataset include] contient les définitions de deux dimensions étendues, le mappage affiche un noeud vert représentant les deux dimensions étendues.

## Blocs de transformation {#section-c442730394264a0b850792a32eaaa2da}

Chaque noeud bleu est un bloc de transformation et comporte les options suivantes :

* Pour vue des champs d&#39;entrée du bloc de transformation, cliquez avec le bouton droit de la souris sur le noeud du bloc et cliquez sur **[!UICONTROL Inputs]**.
* Pour vue des champs de sortie du bloc de transformation, cliquez avec le bouton droit de la souris sur le noeud du bloc et cliquez sur **[!UICONTROL Outputs]**.
* Pour modifier l&#39;une des transformations du bloc, cliquez avec le bouton droit de la souris sur le noeud du bloc et cliquez sur **[!UICONTROL Edit Configuration]**. La légende qui s’affiche contient l’intégralité du fichier de configuration dans lequel toutes les transformations sont définies. Vous pouvez ensuite modifier les paramètres selon vos besoins. Pour plus d&#39;informations sur ces paramètres, consultez le *Guide de configuration des jeux de données*.

* Pour afficher toutes les transformations du bloc, cliquez avec le bouton droit de la souris sur le noeud du bloc de transformation et cliquez sur **[!UICONTROL Show Details]**. La légende qui s’affiche contient un autre mappage de dépendances montrant les noeuds pour toutes les transformations du bloc.

## Blocs de Dimension {#section-0dd581ac6dfc4153bee5300b3cfae2a0}

Chaque noeud vert est un bloc de dimension et dispose des options suivantes :

* Pour vue des champs d&#39;entrée ou de la dimension parente du bloc de dimension, cliquez avec le bouton droit de la souris sur le noeud du bloc, puis cliquez sur **[!UICONTROL Inputs]**.
* Pour vue des dimensions de sortie du bloc de dimension, cliquez avec le bouton droit de la souris sur le noeud du bloc et cliquez sur **[!UICONTROL Outputs]**.
