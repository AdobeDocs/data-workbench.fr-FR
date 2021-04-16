---
description: Informations sur les différents types de mappages de processus.
title: Types des cartographies des processus
uuid: 19473b77-13c1-4829-b018-d3316e434ba4
exl-id: 8bac7036-c7fe-4566-8e59-08e1ddc7ddb7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 1%

---

# Types des cartographies des processus{#types-of-process-maps}

Informations sur les différents types de mappages de processus.

## Mappages de processus 2D {#section-ea7fbdb80b1b44aebcd9e4090b6540bf}

Les cartes de processus bidimensionnelles fournissent une vue bidimensionnelle de l’activité entre les éléments de dimension. La taille d’un noeud dans un mappage de processus 2D est proportionnelle à la valeur de la mesure associée à ce noeud. En outre, l’épaisseur et l’intensité d’une flèche entre deux noeuds sont proportionnelles à la moyenne des valeurs de la mesure pour ces noeuds.

Dans un mappage de processus 2D, vous pouvez effectuer l’une des tâches suivantes :

* Sélection, déplacement, suppression et libellé des noeuds
* Effectuer des sélections
* Enregistrer les dimensions
* Créer d’autres visualisations
* Activer les liens de couleur
* Afficher les quantités de mesure
* Légendes Ajoutées

La carte de processus 2D de l&#39;exemple suivant montre les noeuds correspondant aux noms des films. Chaque nom de film est un élément de la dimension Film, qui est défini dans un jeu de données constitué de données de film. La dimension Film est la dimension de base de ce mappage de processus.

![](assets/vis_2DProcessMap_MovieNodes.png)

Dans l’exemple, la taille de chaque noeud, ainsi que l’épaisseur et l’intensité de chaque flèche sont proportionnelles à la mesure Classifications, qui est le nombre d’évaluations reçues par un film. Par conséquent, un film avec un grand noeud, tel que *Fête de l’Indépendance*, a plus d’évaluations qu’un film avec un petit noeud, tel que *Événement Horizon*. Vous pouvez également constater que plus de téléspectateurs ont évalué *le jour de l&#39;indépendance* avant *Cold Mountain* que les mêmes films dans l&#39;ordre inverse. Notez que les flèches n’indiquent pas que les visiteurs ont noté *Jour de l’Indépendance* puis *Cold Mountain* immédiatement après, ou vice versa. Les visiteurs ont peut-être coté d’autres films entre les deux, mais ces films ne sont pas affichés sur cette carte.

## Mappages de mesures 2D {#section-a9b846fc71224058918fbc378315effe}

Les cartes de mesures bidimensionnelles sont un type de carte de processus 2D qui positionne les noeuds en fonction de la valeur d’une mesure particulière. Dans de nombreux cas, la mesure utilisée avec la carte de mesure 2D est Conversion ou Rétention. Les cartes de conversion et de rétention vous aident à comprendre quelles étapes des processus de vos canaux orientés vers le client influencent la conversion et la rétention des clients.

>[!NOTE]
>
>La mesure que vous utilisez avec une carte de mesure 2D doit être exprimée en pourcentage.

Dans une carte des mesures de conversion, les noeuds avec une conversion de 0 % sont tracés à gauche du graphique et les pages avec une conversion de 100 % sont tracées à droite. L’Activité entre les noeuds s’affiche, ce qui permet de déterminer facilement les étapes d’un processus conduisant à une augmentation ou à une diminution des conversions et celles qui conduisent à l’abandon. Une analyse de conversion de processus est un moyen efficace de comparer des processus ou de comparer différentes implémentations d’un même processus.

![](assets/vis_2DMetricMap_Conversion.png)

De même, les cartes de rétention montrent des éléments avec une rétention de 0 % à gauche du graphique et des éléments avec une rétention de 100 % à droite. Vous pouvez afficher le taux de rétention de chaque noeud sur la carte, ce qui vous permet de déterminer quels éléments influencent les clients à renvoyer.

![](assets/vis_2DMetricMap_Retention.png)

>[!NOTE]
>
>Vous ne pouvez pas déplacer les noeuds sur les cartes de mesure 2D horizontalement. Les cartes de mesures sont conçues pour positionner les noeuds de gauche à droite en fonction de leurs valeurs de mesures.

## Cartes de processus 3D {#section-80acb63ea0994af1af7faef3c6264e51}

Les cartes tridimensionnelles de processus fournissent une vue tridimensionnelle de l’activité entre les éléments de dimension. La hauteur d’une barre dans une carte de processus 3D est proportionnelle à la valeur de la mesure associée à ce noeud. Comme pour les mappages de processus 2D, l’épaisseur et l’intensité des connecteurs entre deux noeuds sont proportionnelles à la moyenne des valeurs de la mesure pour ces noeuds. Dans une carte de processus 3D, vous pouvez effectuer l’une des tâches suivantes :

* Sélection, déplacement, suppression et libellé des noeuds
* Effectuer des sélections
* Enregistrer les dimensions
* Créer d’autres visualisations
* Activer les liens de couleur

La carte de processus 3D de l&#39;exemple suivant montre les noeuds correspondant aux pages d&#39;un site Web. Chaque page est un élément de la dimension Page, qui est défini dans un jeu de données constitué de données de trafic Web. La dimension Page est la dimension de base de ce mappage de processus.

![](assets/vis_3DProcessMap_PageNodes.png)

Dans l’exemple, la hauteur de chaque barre et l’épaisseur et l’intensité de chaque connecteur sont proportionnelles à la mesure Sessions, soit le nombre de sessions au cours desquelles les pages ont été consultées. Par conséquent, une page avec une barre haute, telle que /faq/all/FAQ, a été consultée pendant plus de sessions qu’une page avec une barre courte, telle que /vs/demo. Notez que les connexions entre deux pages n’indiquent pas qu’une page a été consultée immédiatement avant ou après une autre au cours d’une session donnée. D’autres pages ont peut-être été consultées au cours de la même session, mais elles ne sont pas affichées sur cette carte.
