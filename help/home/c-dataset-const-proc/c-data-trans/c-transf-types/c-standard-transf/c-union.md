---
description: La transformation d’Union prend un ensemble d’entrées et crée un vecteur de chaînes comme sortie.
title: Union
uuid: 2f8bd332-727e-4a4e-a3e7-a52ea2b0a33a
exl-id: 841b5133-d587-409c-b39e-47169beb2ddf
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 3%

---

# Union{#union}

La transformation d’Union prend un ensemble d’entrées et crée un vecteur de chaînes comme sortie.

Si l’une des entrées est elle-même un vecteur, chaque élément du vecteur d’entrée est associé à un élément du vecteur de sortie (c’est-à-dire que la transformation ne crée pas de vecteur de vecteurs).

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez entrer n&#39;importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d&#39;application de cette transformation. |  |
| Par défaut | Valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible. |  |
| Entrées | Une ou plusieurs valeurs d’entrée. |  |
| Sortie | Nom du champ de sortie. |  |

Cet exemple utilise des champs de données provenant du trafic du site Web pour créer une liste des codes postaux associés aux visiteurs du site Web (c&#39;est-à-dire, dans chaque entrée de journal). Les données fournissent deux sources possibles pour ces informations : l&#39;un dans cs-uri-requête et l&#39;autre dans un champ [!DNL zipcode] du cookie. Si aucun de ces champs ne contient de code postal, la valeur par défaut de 00000 est utilisée.

![](assets/cfg_TransformationType_Union.png)

Bien qu’il soit possible que ces deux valeurs soient disponibles dans une seule entrée de journal, vous pouvez sélectionner la valeur à utiliser lorsque vous créez une dimension basée sur la sortie de la transformation. Dans un cas d’utilisation typique, vous créez une dimension simple qui prend la première ou la dernière des valeurs rencontrées. Pour plus d’informations sur la création de dimensions simples, voir [Dimensions étendues](../../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).
