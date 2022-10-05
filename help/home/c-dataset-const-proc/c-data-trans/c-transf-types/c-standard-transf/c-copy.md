---
description: La transformation Copier copie simplement la valeur du champ de saisie dans le champ de sortie donné. Si le champ d’entrée peut être un vecteur de chaînes, le champ de sortie doit commencer par "x-".
title: Copier
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
exl-id: 04e97006-1e8e-4123-bbbc-b90a5231170f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 6%

---

# Copier{#copy}

{{eol}}

La transformation Copier copie simplement la valeur du champ de saisie dans le champ de sortie donné. Si le champ d’entrée peut être un vecteur de chaînes, le champ de sortie doit commencer par &quot;x-&quot;.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Les conditions dans lesquelles cette transformation est appliquée. |  |
| Par défaut | Utilisé si le test de condition est vrai et que la valeur d’entrée n’est pas disponible dans l’entrée de journal donnée. |  |
| Entrée | Nom du champ à partir duquel copier. |  |
| Sortie | Nom du champ de sortie. |  |

Dans cet exemple, qui utilise des champs de données collectées à partir du trafic du site web, le champ de sortie, x-purchase-success, reçoit la valeur littérale de &quot;1&quot; chaque fois que cs-uri-stem correspond à [!DNL /checkout/confirmed.php]. Si la variable [!DNL Condition] n’est pas satisfait (c’est-à-dire que cs-uri-stem ne correspond pas à [!DNL /checkout/confirmed.php]), x-purchase-success n’est pas modifié.

![](assets/cfg_TransformationType_Copy.png)
