---
description: Informations conceptuelles sur les sous-ensembles.
title: Compréhension des sous-ensembles
uuid: ed185b63-dbb3-4ed4-9403-cf4dc8be2ff1
exl-id: a75b36f9-d34d-4a4a-8a2c-15ae5461823c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---

# Compréhension des sous-ensembles{#understanding-subsets}

Informations conceptuelles sur les sous-ensembles.

Lors de l’utilisation d’un sous-ensemble, gardez à l’esprit les points suivants :

* Tous vos points de repère concernent désormais votre sous-ensemble, et non l’ensemble du jeu de données, ce qui est beaucoup plus utile lors de l’analyse d’un sous-ensemble spécifique. Voir [Présentation des repères](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).
* L’utilisation d’un sous-ensemble affecte tous vos espaces de travail, car le sous-ensemble est appliqué globalement au Data Workbench.
* Les sous-ensembles affectent uniquement les mesures et les dimensions Denormal, pas les dimensions normales.
* Lors de l’utilisation de [!DNL Report], les sous-ensembles n’affectent pas les données des rapports publiés pour d’autres utilisateurs à la vue.
* Une fois appliqué, votre sous-ensemble est en vigueur pour toutes les tâches ultérieures du profil, y compris la prochaine fois que vous ouvrirez cette instance de Data Workbench, jusqu’à ce que vous la supprimiez.
* Le seul endroit qui indique qu&#39;un sous-ensemble a été appliqué est le menu contextuel que vous atteignez en cliquant avec le bouton droit dans un espace de travail.

   ![](assets/mnu_Subset.png)

* Vous devez travailler en ligne pour modifier ou supprimer un sous-ensemble. Si vous travaillez hors ligne et avez appliqué un sous-ensemble, vous ne pouvez pas vue les résultats de l’ensemble de données. Voir [Travail hors connexion et en ligne](../../../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

   >[!NOTE]
   >
   >La taille de votre sous-ensemble est limitée à la quantité de données de votre filtre qui réside sur un seul serveur de Data Workbench. Par conséquent, si votre jeu de données s’étend sur une grappe de serveurs Data Workbench, les données de votre sous-ensemble proviennent d’un seul serveur Data Workbench de la grappe.

Un utilisateur d’un grand détaillant souhaite créer un sous-ensemble (cache local) d’une semaine de travail donnée de données, puis exécuter des requêtes uniquement sur cette semaine de données. Pour ce faire, l’utilisateur crée un sous-ensemble pour les jours d’intérêt.

L&#39;exemple suivant montre un graphique à barres de Visiteurs au fil du temps et une légende de mesure Trafic. La première figure ne contient aucune sélection : toutes les données du jeu de données sont représentées. La seconde figure présente les données d’un sous-ensemble de jours = {..} par Visiteur, dans lequel Days est basé sur une sélection des éléments 1er avril au 5 avril dans la dimension Day.

![](assets/client-sub1.png)
