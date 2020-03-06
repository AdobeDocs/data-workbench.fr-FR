---
description: La transformation PullNameValues est une opération spéciale qui prend les valeurs du champ cs-uri-query et sépare chacune des paires nom-valeur en une chaîne distincte.
solution: Analytics
title: PullNameValues
topic: Data workbench
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# PullNameValues{#pullnamevalues}

La transformation PullNameValues est une opération spéciale qui prend les valeurs du champ cs-uri-query et sépare chacune des paires nom-valeur en une chaîne distincte.

L’ensemble des chaînes de paires nom-valeur est généré dans le champ de sortie spécifié sous la forme d’un vecteur de chaînes.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez saisir n’importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d’application de cette transformation. |  |
| Par défaut | Valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible dans l’entrée de journal donnée. |  |
| Sortie | Nom de la chaîne de sortie. |  |

La [!DNL PullNameValues] transformation est utilisée dans cet exemple pour capturer l’utilisation du formulaire de recherche par les visiteurs : les boutons sélectionnés, les valeurs saisies dans le formulaire, etc. L’exemple utilise une [!DNL String Match] condition (voir [Conditions](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) pour isoler l’utilisation de cette transformation vers la page uniquement [!DNL /search.php]. Le vecteur des paires nom-valeur est généré dans le champ x-recherche-nom-valeurs.

![](assets/cfg_TransformationType_PullNameValues.png)

En utilisant la transformation définie ci-dessus, si le champ cs-uri-stem correspondait à la page [!DNL /search.php] et cs-uri-query contenait les éléments suivants :

* Recherche=Bob&amp;State=Virginia&amp;isMale=true

les valeurs x-search-name contiennent alors un vecteur contenant les trois chaînes suivantes :

* Recherche=Bob
* État=Virginie
* isMale=true

