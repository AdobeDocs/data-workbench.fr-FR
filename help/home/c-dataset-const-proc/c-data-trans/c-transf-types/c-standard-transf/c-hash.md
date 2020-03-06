---
description: La transformation de hachage crée une chaîne presque unique représentant un nombre 64 bits à partir des valeurs d’entrée.
solution: Analytics
title: Hachage
topic: Data workbench
uuid: 13bc14e6-75e2-4711-8f98-50fd18802be5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Hachage{#hash}

La transformation de hachage crée une chaîne presque unique représentant un nombre 64 bits à partir des valeurs d’entrée.

Cette transformation fournit la même valeur de hachage lorsqu’elle reçoit les mêmes entrées.

>[!NOTE]
>
>La valeur obtenue est presque unique car la transformation utilise un nombre 64 bits comme espace des valeurs de hachage possibles. Pour un million d&#39;entrées uniques à la [!DNL hash] transformation, il y a 1 chance sur 38 000 000 d&#39;obtenir une valeur de hachage en double.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d’application de cette transformation. |  |
| Par défaut | Valeur par défaut à utiliser si la valeur d’entrée n’est pas disponible. |  |
| Entrées | Jeu d’entrées à utiliser pour créer la valeur de hachage. |  |
| Sortie | Nom du champ pour la sortie. |  |

Dans cet exemple, les valeurs des champs c-ip et cs(user-agent) sont utilisées pour créer un ID de suivi, qui est stocké dans le champ x-trackingid.

![](assets/cfg_TransformationType_Hash.png)

>[!NOTE]
>
>Cet exemple ne représente pas une solution idéale pour créer des ID de suivi uniques. Toutefois, dans les cas où les informations du journal d&#39;archivage sont utilisées, il peut s&#39;agir de la meilleure méthode.

