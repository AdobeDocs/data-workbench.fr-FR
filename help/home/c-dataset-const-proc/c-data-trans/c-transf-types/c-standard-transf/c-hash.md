---
description: La transformation de hachage crée une chaîne presque unique représentant un nombre 64 bits à partir des valeurs d’entrée.
title: Hash
uuid: 13bc14e6-75e2-4711-8f98-50fd18802be5
exl-id: 6912a1d2-9ae8-42ba-94bd-a7a28cbdfae6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 5%

---

# Hash{#hash}

{{eol}}

La transformation de hachage crée une chaîne presque unique représentant un nombre 64 bits à partir des valeurs d’entrée.

Cette transformation fournit la même valeur de hachage lorsqu’on leur donne les mêmes entrées.

>[!NOTE]
>
>La valeur obtenue est presque unique, car la transformation utilise un nombre 64 bits comme espace des valeurs de hachage possibles. Pour un million d’entrées uniques au [!DNL hash] transformation : il y a 1 sur 38 000 000 chances d’obtenir une valeur de hachage en double.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Les conditions dans lesquelles cette transformation est appliquée. |  |
| Par défaut | Valeur par défaut à utiliser si la valeur d’entrée n’est pas disponible. |  |
| Entrées | Jeu d’entrées à utiliser pour créer la valeur de hachage. |  |
| Sortie | Nom du champ pour la sortie. |  |

Dans cet exemple, les valeurs des champs c-ip et cs(user-agent) sont utilisées pour créer un ID de suivi, qui est stocké dans le champ x-trackingid .

![](assets/cfg_TransformationType_Hash.png)

>[!NOTE]
>
>Cet exemple ne représente pas une solution idéale pour la création d’identifiants de suivi uniques. Cependant, dans les cas où des informations de journal d’archivage sont utilisées, il peut s’agir de la meilleure méthode.
