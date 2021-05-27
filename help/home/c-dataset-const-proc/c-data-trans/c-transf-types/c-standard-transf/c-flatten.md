---
description: La transformation Aplatissement prend un vecteur de chaînes et mappe chaque valeur dans son propre champ.
title: Flatten
uuid: 00b06a5c-506b-45fe-9773-44d65b8ec233
exl-id: 63f3e4bc-238f-4e15-8ae5-2f805bd080d3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Aplatissement{#flatten}

La transformation Aplatissement prend un vecteur de chaînes et mappe chaque valeur dans son propre champ.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Les conditions dans lesquelles cette transformation est appliquée. |  |
| Par défaut | La valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible pour l’entrée de journal. |  |
| Entrée | Un vecteur de valeurs string à mapper aux noms des champs de sortie. |  |
| Sorties | Ensemble de noms de champs de sortie. |  |

Considérations pour [!DNL Flatten]

* Si le vecteur d’entrée contient plus de valeurs que les champs de sortie définis, les valeurs d’entrée supplémentaires sont simplement ignorées.
* Si le vecteur d’entrée contient moins de valeurs que les champs de sortie définis, la valeur par défaut (si elle est définie) est attribuée aux champs de sortie supplémentaires, ou une chaîne vide si aucune valeur par défaut n’est définie.

Ici, la transformation [!DNL Flatten] est utilisée pour prendre un vecteur de produits (x-products) et les séparer en quatre champs (x-product1, ..., x-product4).

![](assets/cfg_TransformationType_Flatten.png)

Si la valeur d’entrée contenait les chaînes B57481, C46355 et Z97123, les champs de sortie auraient les valeurs suivantes :

* x-product1 = B57481
* x-product2 = C46355
* x-product3 = Z97123
* x-product4 = Vide (il y a plus d’entrées que de sorties et aucune valeur par défaut n’est spécifiée.)
