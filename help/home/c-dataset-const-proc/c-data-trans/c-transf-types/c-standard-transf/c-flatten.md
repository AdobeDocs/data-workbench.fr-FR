---
description: La transformation d’aplatissement utilise un vecteur de chaînes et mappe chaque valeur dans son propre champ.
solution: Analytics
title: Aplatir
topic: Data workbench
uuid: 00b06a5c-506b-45fe-9773-44d65b8ec233
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aplatir{#flatten}

La transformation d’aplatissement utilise un vecteur de chaînes et mappe chaque valeur dans son propre champ.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d’application de cette transformation. |  |
| Par défaut | Valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible pour l’entrée du journal. |  |
| Entrée | Vecteur de valeurs de chaîne à mapper aux noms des champs de sortie. |  |
| Sorties | Ensemble de noms de champ de sortie. |  |

Remarques concernant [!DNL Flatten]

* Si le vecteur d’entrée contient plus de valeurs qu’il n’y a de champs de sortie définis, les valeurs d’entrée supplémentaires sont simplement ignorées.
* Si le vecteur d’entrée contient moins de valeurs qu’il n’y a de champs de sortie définis, la valeur par défaut (le cas échéant) est attribuée aux champs de sortie supplémentaires ou une chaîne vide si aucune valeur par défaut n’est définie.

Ici, la [!DNL Flatten] transformation est utilisée pour prendre un vecteur de produits (x-products) et les séparer en quatre champs (x-product1, ..., x-product4).

![](assets/cfg_TransformationType_Flatten.png)

Si la valeur d’entrée contenait les chaînes B57481, C46355 et Z97123, les valeurs des champs de sortie seraient les suivantes :

* x-product1 = B57481
* x-product2 = C46355
* x-product3 = Z97123
* x-product4 = Vide (Il y a plus d’entrées que de sorties et aucune valeur par défaut n’est spécifiée.)

