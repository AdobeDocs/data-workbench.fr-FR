---
description: La transformation de l'Union prend un ensemble d'entrées et crée un vecteur de chaînes comme sortie.
solution: Analytics
title: Union
topic: Data workbench
uuid: 2f8bd332-727e-4a4e-a3e7-a52ea2b0a33a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Union{#union}

La transformation de l&#39;Union prend un ensemble d&#39;entrées et crée un vecteur de chaînes comme sortie.

Si l’une des entrées est elle-même un vecteur, chaque élément du vecteur d’entrée est associé à un élément du vecteur de sortie (autrement dit, la transformation ne crée pas de vecteur de vecteurs).

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d’application de cette transformation. |  |
| Par défaut | Valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible. |  |
| Entrées | Une ou plusieurs valeurs d’entrée. |  |
| Sortie | Nom du champ de sortie. |  |

Cet exemple utilise des champs de données provenant du trafic du site Web pour créer une liste des codes postaux associés aux visiteurs du site Web (c&#39;est-à-dire, dans chaque entrée du journal). Les données fournissent deux sources possibles pour ces informations : l&#39;une dans cs-uri-query et l&#39;autre dans un [!DNL zipcode] champ du cookie. Si aucun de ces champs ne contient de code postal, la valeur par défaut de 00000 est utilisée.

![](assets/cfg_TransformationType_Union.png)

Bien qu’il soit possible que ces deux valeurs soient disponibles dans une seule entrée de journal, vous pouvez sélectionner la valeur à utiliser lorsque vous créez une dimension en fonction de la sortie de la transformation. Dans un cas d’utilisation type, vous créeriez une dimension simple qui prend la première ou la dernière des valeurs rencontrées. Pour plus d’informations sur la création de dimensions simples, voir Dimensions [étendues](../../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).
