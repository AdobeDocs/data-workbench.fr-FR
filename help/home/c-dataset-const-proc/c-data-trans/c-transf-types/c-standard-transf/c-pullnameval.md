---
description: La transformation PullNameValues est une opération spéciale qui prend les valeurs du champ cs-uri-requête et sépare chacune des paires nom-valeur en une chaîne distincte.
title: PullNameValues
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
exl-id: 3660ff6e-87dc-42cf-a897-0e2e0e021c07
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 4%

---

# PullNameValues{#pullnamevalues}

La transformation PullNameValues est une opération spéciale qui prend les valeurs du champ cs-uri-requête et sépare chacune des paires nom-valeur en une chaîne distincte.

La collection complète de chaînes de paires nom-valeur est générée dans le champ de sortie spécifié en tant que vecteur de chaînes.

| Paramètre | Description | Par défaut |
|---|---|---|
| Nom | Nom descriptif de la transformation. Vous pouvez entrer n&#39;importe quel nom ici. |  |
| Commentaires | Facultatif. Remarques sur la transformation. |  |
| Condition | Conditions d&#39;application de cette transformation. |  |
| Par défaut | Valeur par défaut à utiliser si la condition est remplie et que la valeur d’entrée n’est pas disponible dans l’entrée de journal donnée. |  |
| Sortie | Nom de la chaîne de sortie. |  |

La transformation [!DNL PullNameValues] est utilisée dans cet exemple pour capturer l&#39;utilisation par les visiteurs du formulaire de recherche : les boutons sélectionnés, les valeurs saisies dans le formulaire, etc. L&#39;exemple utilise une condition [!DNL String Match] (voir [Conditions](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) pour isoler l&#39;utilisation de cette transformation dans la seule page [!DNL /search.php]. Le vecteur des paires nom-valeur est généré dans le champ x-search-name-values.

![](assets/cfg_TransformationType_PullNameValues.png)

En utilisant la transformation définie ci-dessus, si le champ cs-uri-stem correspondait à la page [!DNL /search.php] et cs-uri-requête contenait les éléments suivants :

* Recherche=Bob&amp;State=Virginia&amp;isMale=true

alors x-search-name-values contient un vecteur contenant les trois chaînes suivantes :

* Recherche=Bob
* État=Virginie
* isMale=true
