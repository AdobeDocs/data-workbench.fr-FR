---
description: Les transformations vous permettent d’extraire les informations disponibles dans vos fichiers de données et de les manipuler dans un formulaire plus utile.
solution: Analytics
title: A propos des transformations
topic: Data workbench
uuid: 9366f607-741d-4512-9e1b-4165f4291246
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# A propos des transformations{#about-transformations}

Les transformations vous permettent d’extraire les informations disponibles dans vos fichiers de données et de les manipuler dans un formulaire plus utile.

Les transformations opèrent sur les entrées du journal (vous pouvez considérer les entrées du journal comme des lignes de données) dans vos sources de journal. Pour chaque ligne de données, la transformation prend la valeur du champ d’entrée spécifié, effectue un ensemble d’étapes de traitement et enregistre le résultat dans le champ de sortie que vous spécifiez. Vous pouvez définir les transformations à exécuter pendant la phase de traitement du journal ou de transformation du processus de construction du jeu de données :

* **Pendant le traitement du journal :** Les transformations effectuées pendant la phase de traitement du journal de la construction des jeux de données sont appliquées à chaque enregistrement de données d’événement (entrée de journal) pour mettre à jour les champs du journal existants ou produire de nouveaux champs. Les résultats des transformations sont utilisés avec les conditions d’entrée du journal pour évaluer les entrées du journal qui sont filtrées hors du jeu de données pendant le traitement du journal.
* **Pendant la transformation :** Les transformations effectuées au cours de la phase de transformation de la construction des jeux de données opèrent sur les champs des données transmises par le traitement des journaux afin de créer des dimensions étendues que vous pouvez utiliser dans vos analyses. Voir Dimensions [étendues](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

>[!NOTE]
>
>L’entrée des données à la transformation à partir du traitement du journal est triée par temps et regroupée par ID de suivi dans vos données source. Plusieurs transformations nécessitent que les données se trouvent dans ce formulaire et fonctionnent uniquement lorsqu’elles sont définies dans au cours de la transformation.

Les modifications apportées aux transformations doivent être faites avec soin. Les transformations n&#39;affectent pas les entrées de journal qui s&#39;enchaînent dans le processus de construction des jeux de données, mais elles affectent les résultats présentés. Cela permet de modifier les éléments analysés sans modifier les données sur lesquelles repose l’analyse. Toutefois, les changements dans les transformations peuvent modifier fondamentalement les valeurs produites dans les analyses.
