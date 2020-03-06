---
description: Informations conceptuelles sur les sous-ensembles.
solution: Analytics
title: Présentation des sous-ensembles
topic: Data workbench
uuid: ed185b63-dbb3-4ed4-9403-cf4dc8be2ff1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Présentation des sous-ensembles{#understanding-subsets}

Informations conceptuelles sur les sous-ensembles.

Lors de l’utilisation d’un sous-ensemble, gardez à l’esprit les points suivants :

* Tous vos points de repère concernent désormais votre sous-ensemble, et non l’ensemble du jeu de données, ce qui est beaucoup plus utile lors de l’analyse d’un sous-ensemble spécifique. Voir [Présentation des tests](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).
* L’utilisation d’un sous-ensemble affecte tous vos espaces de travail, car il est appliqué globalement aux Outils de données.
* Les sous-ensembles affectent uniquement les mesures et les dimensions dénormalisées, et non les dimensions normales.
* Lors de [!DNL Report]l’utilisation, les sous-ensembles n’affectent pas les données des rapports publiés pour que d’autres les voient.
* Une fois appliqué, votre sous-ensemble est en vigueur pour toutes les tâches ultérieures du profil, y compris la prochaine fois que vous ouvrirez cette instance des Outils de données, jusqu’à ce que vous la supprimiez.
* Le seul endroit qui indique qu’un sous-ensemble a été appliqué est le menu contextuel que vous atteignez en cliquant avec le bouton droit dans un espace de travail.

   ![](assets/mnu_Subset.png)

* Vous devez travailler en ligne pour modifier ou supprimer un sous-ensemble. Si vous travaillez hors ligne et avez appliqué un sous-ensemble, vous ne pouvez pas afficher les résultats de l’ensemble des jeux de données. Voir [Travail hors connexion et en ligne](../../../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54).

   >[!NOTE]
   >
   >La taille de votre sous-ensemble est limitée à la quantité de données dans votre filtre qui réside sur un seul serveur Outils de données. Par conséquent, si votre jeu de données s’étend sur une grappe de serveurs Outils de données, les données de votre sous-ensemble proviennent d’un seul serveur Outils de données de la grappe.

Un utilisateur d’un grand détaillant souhaite créer un sous-ensemble (cache local) d’une semaine de travail particulière de données, puis exécuter des requêtes uniquement sur cette semaine de données. Pour ce faire, l’utilisateur crée un sous-ensemble pour les jours d’intérêt.

L’exemple suivant montre un graphique à barres de visiteurs au fil du temps et une légende de mesure Trafic. La première figure ne contient aucune sélection : toutes les données du jeu de données sont représentées. La seconde figure présente les données d’un sous-ensemble de jours = {...} par les visiteurs, dans lequel Days est basé sur une sélection des éléments 1er avril au 5 avril dans la dimension Day.

![](assets/client-sub1.png)

