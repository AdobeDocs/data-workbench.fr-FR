---
description: La transformation ChangeCase modifie la casse de la chaîne dans le paramètre Input, comme spécifié par le paramètre Action.
solution: Analytics
title: ChangeCase
topic: Data workbench
uuid: 676e79e6-324e-43d1-8982-b44596d0eeac
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ChangeCase{#changecase}

La transformation ChangeCase modifie la casse de la chaîne dans le paramètre Input, comme spécifié par le paramètre Action.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Action | Supérieur ou inférieur. Indique si la casse doit être remplacée par une majuscule ou une minuscule. | lower |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d’application de cette transformation. |  |
| Entrée | Nom du champ de l’entrée de journal à utiliser comme entrée. |  |
| Sortie | Nom du champ de sortie. |  |

Dans cet exemple, qui utilise les champs de données collectées à partir du trafic du site Web, la casse de la chaîne dans le champ s-dns est remplacée par la minuscule et la nouvelle valeur est générée dans le nouveau champ, x-lowercase-dns.

![](assets/cfg_TransformationType_ChangeCase.png)

