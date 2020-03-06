---
description: Lorsque vous affichez les composants de jeux de données sur un mappage de dépendances, vous avez la possibilité d’activer l’option d’affichage Inclure les blocs de fichiers.
solution: Analytics
title: Blocs de fichier
topic: Data workbench
uuid: 079dccba-ef19-4895-90bb-6c56f26e8beb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Blocs de fichier{#file-blocks}

Lorsque vous affichez les composants de jeux de données sur un mappage de dépendances, vous avez la possibilité d’activer l’option d’affichage Inclure les blocs de fichiers.

Lorsque cette option est activée, le mappage affiche un noeud bleu unique pour toutes les transformations définies dans un fichier de configuration de jeu de données et un noeud vert unique pour toutes les dimensions étendues définies dans un fichier de configuration de jeu de données. Par exemple, si un [!DNL log processing dataset include] fichier comprend les définitions de trois transformations, le mappage affiche un noeud bleu représentant les trois transformations. De même, si un [!DNL transformation dataset include] fichier comprend les définitions de deux dimensions étendues, le mappage affiche un noeud vert représentant les deux dimensions étendues.

## Blocs de transformation {#section-c442730394264a0b850792a32eaaa2da}

Chaque noeud bleu est un bloc de transformation et comporte les options suivantes :

* Pour afficher les champs d’entrée du bloc de transformation, cliquez avec le bouton droit de la souris sur le noeud du bloc, puis cliquez sur **[!UICONTROL Inputs]**.
* Pour afficher les champs de sortie du bloc de transformation, cliquez avec le bouton droit de la souris sur le noeud du bloc, puis cliquez sur **[!UICONTROL Outputs]**.
* Pour modifier l’une des transformations du bloc, cliquez avec le bouton droit de la souris sur le noeud du bloc, puis cliquez sur **[!UICONTROL Edit Configuration]**. La légende qui s’affiche contient l’intégralité du fichier de configuration dans lequel toutes les transformations sont définies. Vous pouvez ensuite modifier les paramètres suivant vos besoins. Pour plus d&#39;informations sur ces paramètres, consultez le Guide *de configuration des jeux de* données.

* Pour afficher toutes les transformations du bloc, cliquez avec le bouton droit de la souris sur le noeud du bloc de transformation, puis cliquez sur **[!UICONTROL Show Details]**. La légende qui s’affiche contient un autre mappage de dépendances montrant les noeuds pour toutes les transformations du bloc.

## Blocs de dimension {#section-0dd581ac6dfc4153bee5300b3cfae2a0}

Chaque noeud vert est un bloc de dimension et comporte les options suivantes :

* Pour afficher les champs d’entrée ou la dimension parent du bloc de dimension, cliquez avec le bouton droit de la souris sur le noeud du bloc, puis cliquez sur **[!UICONTROL Inputs]**.
* Pour afficher les dimensions de sortie du bloc de dimension, cliquez avec le bouton droit de la souris sur le noeud du bloc, puis cliquez sur **[!UICONTROL Outputs]**.

