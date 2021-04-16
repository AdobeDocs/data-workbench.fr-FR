---
description: La transformation de hachage crée une chaîne presque unique représentant un nombre 64 bits à partir des valeurs d’entrée.
title: Hash
uuid: 13bc14e6-75e2-4711-8f98-50fd18802be5
exl-id: 6912a1d2-9ae8-42ba-94bd-a7a28cbdfae6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 4%

---

# Hash{#hash}

La transformation de hachage crée une chaîne presque unique représentant un nombre 64 bits à partir des valeurs d’entrée.

Cette transformation fournit la même valeur de hachage lorsqu’on lui attribue les mêmes entrées.

>[!NOTE]
>
>La valeur obtenue est presque unique car la transformation utilise un nombre 64 bits comme espace des valeurs de hachage possibles. Pour un million d&#39;entrées uniques à la transformation [!DNL hash], il y a 1 chance sur 38 000 000 d&#39;obtenir une valeur de hachage duplicata.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez entrer n&#39;importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d&#39;application de cette transformation. |  |
| Par défaut | Valeur par défaut à utiliser si la valeur d’entrée n’est pas disponible. |  |
| Entrées | Jeu d’entrées à utiliser pour créer la valeur de hachage. |  |
| Sortie | Nom du champ pour la sortie. |  |

Dans cet exemple, les valeurs des champs c-ip et cs(user-agent) sont utilisées pour créer un identifiant de suivi, qui est stocké dans le champ x-trackingid.

![](assets/cfg_TransformationType_Hash.png)

>[!NOTE]
>
>Cet exemple ne représente pas une solution idéale pour créer des ID de suivi uniques. Toutefois, dans les cas où les informations consignées dans les archives sont utilisées, il peut s&#39;agir de la meilleure méthode.
