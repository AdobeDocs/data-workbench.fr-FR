---
description: La transformation ChangeCase modifie la casse de la chaîne dans le paramètre Input , comme indiqué par le paramètre Action .
title: ChangeCase
uuid: 676e79e6-324e-43d1-8982-b44596d0eeac
exl-id: 2002fe22-d31c-4286-9f73-59ef205f1384
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 8%

---

# ChangeCase{#changecase}

{{eol}}

La transformation ChangeCase modifie la casse de la chaîne dans le paramètre Input , comme indiqué par le paramètre Action .

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Action | Supérieur ou inférieur. Indique si la casse doit être changée en majuscule ou en minuscule. | lower |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Les conditions dans lesquelles cette transformation est appliquée. |  |
| Entrée | Nom du champ de l’entrée de journal à utiliser comme entrée. |  |
| Sortie | Nom du champ de sortie. |  |

Dans cet exemple, qui utilise les champs de données collectées à partir du trafic du site web, la casse de la chaîne dans le champ s-dns est remplacée par une minuscule et la nouvelle valeur est générée dans le nouveau champ x-lowercase-dns.

![](assets/cfg_TransformationType_ChangeCase.png)
