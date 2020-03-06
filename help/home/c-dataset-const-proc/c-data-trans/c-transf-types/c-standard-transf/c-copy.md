---
description: La transformation Copier copie simplement la valeur du champ d’entrée dans le champ de sortie donné. Si le champ d’entrée peut être un vecteur de chaînes, le champ de sortie doit commencer par "x-".
solution: Analytics
title: Copier
topic: Data workbench
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Copier{#copy}

La transformation Copier copie simplement la valeur du champ d’entrée dans le champ de sortie donné. Si le champ d’entrée peut être un vecteur de chaînes, le champ de sortie doit commencer par &quot;x-&quot;.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d’application de cette transformation. |  |
| Par défaut | Utilisé si le test de condition est vrai et que la valeur d’entrée n’est pas disponible dans l’entrée de journal donnée. |  |
| Entrée | Nom du champ à partir duquel copier. |  |
| Sortie | Nom du champ de sortie. |  |

Dans cet exemple, qui utilise les champs de données collectés à partir du trafic du site Web, le champ de sortie, x-purchase-success, reçoit la valeur littérale de &quot;1&quot; chaque fois que cs-uri-stem correspond [!DNL /checkout/confirmed.php]. Si le [!DNL Condition] n&#39;est pas satisfait (c&#39;est-à-dire que cs-uri-stem ne correspond pas [!DNL /checkout/confirmed.php]), x-purchase-success n&#39;est pas modifié.

![](assets/cfg_TransformationType_Copy.png)

