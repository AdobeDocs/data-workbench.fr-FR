---
description: La transformation PullNameValues est une opération spéciale qui prend les valeurs du champ cs-uri-query et sépare chacune des paires nom-valeur en une chaîne distincte.
title: PullNameValues
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
exl-id: 3660ff6e-87dc-42cf-a897-0e2e0e021c07
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 4%

---

# PullNameValues{#pullnamevalues}

{{eol}}

La transformation PullNameValues est une opération spéciale qui prend les valeurs du champ cs-uri-query et sépare chacune des paires nom-valeur en une chaîne distincte.

La collection complète de chaînes de paires nom-valeur est générée dans le champ de sortie spécifié en tant que vecteur de chaînes.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Les conditions dans lesquelles cette transformation est appliquée. |  |
| Par défaut | La valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible dans l’entrée de journal donnée. |  |
| Sortie | Nom de la chaîne de sortie. |  |

Le [!DNL PullNameValues] La transformation est utilisée dans cet exemple pour capturer l’utilisation du formulaire de recherche par les visiteurs : les boutons sélectionnés, les valeurs saisies dans le formulaire, etc. L’exemple utilise une [!DNL String Match] (voir [Conditions](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) pour isoler l’utilisation de cette transformation par la page uniquement. [!DNL /search.php]. Le vecteur des paires nom-valeur est généré dans le champ x-search-name values.

![](assets/cfg_TransformationType_PullNameValues.png)

En utilisant la transformation définie ci-dessus, si le champ cs-uri-stem correspond à la page. [!DNL /search.php] et cs-uri-query contenait les éléments suivants :

* Recherchez=Bob&amp;State=Virginia&amp;isMale=true

alors x-search-name valeurs contiendra un vecteur contenant les trois chaînes suivantes :

* Recherche=Bob
* Etat=Virginie
* isMale=true
