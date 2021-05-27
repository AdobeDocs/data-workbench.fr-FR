---
description: Informations conceptuelles sur les sous-ensembles.
title: Compréhension des sous-ensembles
uuid: ed185b63-dbb3-4ed4-9403-cf4dc8be2ff1
exl-id: a75b36f9-d34d-4a4a-8a2c-15ae5461823c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---

# Compréhension des sous-ensembles{#understanding-subsets}

Informations conceptuelles sur les sous-ensembles.

Lors de l’utilisation d’un sous-ensemble, veuillez tenir compte des points suivants :

* Tous vos points de repère se rapportent désormais à votre sous-ensemble, et non à l’ensemble du jeu de données, ce qui est beaucoup plus utile lors de l’analyse d’un sous-ensemble spécifique. Voir [Compréhension des références](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).
* L’utilisation d’un sous-ensemble affecte tous vos espaces de travail, car le sous-ensemble est appliqué globalement à Data Workbench.
* Les sous-ensembles affectent uniquement les mesures et les dimensions non normales.
* Lors de l’utilisation de [!DNL Report], les sous-ensembles n’affectent pas les données des rapports publiés pour que d’autres puissent les afficher.
* Une fois appliqué, votre sous-ensemble est appliqué à tous les travaux ultérieurs dans le profil, y compris la prochaine fois que vous ouvrirez cette instance de Data Workbench, jusqu’à ce que vous le supprimiez.
* Le seul endroit qui indique qu’un sous-ensemble a été appliqué est le menu contextuel accessible en cliquant avec le bouton droit de la souris dans un espace de travail.

   ![](assets/mnu_Subset.png)

* Vous devez travailler en ligne pour modifier ou supprimer un sous-ensemble. Si vous travaillez hors ligne et avez appliqué un sous-ensemble, vous ne pouvez pas afficher les résultats du jeu de données entier. Voir [Travail hors ligne et en ligne](../../../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

   >[!NOTE]
   >
   >La taille de votre sous-ensemble est limitée à la quantité de données de votre filtre qui réside sur un seul serveur de Data Workbench. Par conséquent, si votre jeu de données s’étend sur une grappe de serveurs de Data Workbench, les données de votre sous-ensemble proviennent d’un seul serveur de Data Workbench de la grappe.

Un utilisateur d’un grand détaillant souhaite créer un sous-ensemble (cache local) d’une semaine de travail donnée de données, puis exécuter des requêtes uniquement sur cette semaine de données. Pour ce faire, l’utilisateur crée un sous-ensemble pour les jours ciblés.

L’exemple suivant illustre un graphique à barres des visiteurs au fil du temps et une légende des mesures de trafic. La première figure ne contient aucune sélection : toutes les données du jeu de données sont représentées. La seconde figure affiche les données d’un sous-ensemble de jours = {...} par les visiteurs, dans lequel les jours sont basés sur une sélection des éléments 1er avril au 5 avril dans la dimension Jour .

![](assets/client-sub1.png)
