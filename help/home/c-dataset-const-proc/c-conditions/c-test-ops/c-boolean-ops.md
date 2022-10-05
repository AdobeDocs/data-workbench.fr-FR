---
description: Les opérations booléennes combinent les résultats des opérations de test, qui fonctionnent comme des enfants des opérations booléennes.
title: Opérations booléennes
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# Opérations booléennes{#boolean-operations}

{{eol}}

Les opérations booléennes combinent les résultats des opérations de test, qui fonctionnent comme des enfants des opérations booléennes.

Pour plus d’informations sur les opérations de test, voir [Opérations de test](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). Lorsque vous définissez une [!DNL boolean] , vous pouvez définir zéro ou plusieurs enfants pour l’opération.

**Pour ajouter une condition enfant à une opération booléenne**

1. Cliquez avec le bouton droit sur le nom ou le numéro correspondant au [!DNL Boolean] opération.
1. Cliquez sur **[!UICONTROL Add new child]** et sélectionnez l’un des types de condition disponibles à ajouter.
1. Répétez les étapes 1 et 2 jusqu’à ce que vous ayez ajouté toutes les conditions enfants souhaitées pour la variable [!DNL Boolean] opération.

   >[!NOTE]
   >
   >Lorsque vous cliquez avec le bouton droit de la souris sur le nom ou le nombre correspondant à un [!DNL Boolean] l’opération, [!DNL Add new sibling] . Un frère est une autre condition à la même position relative dans la hiérarchie de conditions que la condition [!DNL Boolean] opération sur laquelle vous avez cliqué avec le bouton droit de la souris. Ajout d’un nouveau frère pour un [!DNL Boolean] est identique à l’ajout d’une nouvelle condition en cliquant avec le bouton droit de la souris sur la fonction [!DNL Condition] ou [!DNL Log Entry Condition] .

**Pour supprimer une condition enfant d’une opération booléenne :**

1. Cliquez avec le bouton droit de la souris sur le nom de la condition enfant ou sur le numéro correspondant à la condition enfant que vous souhaitez supprimer du [!DNL Boolean] opération.
1. Cliquez sur **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, où nombre correspond au nombre correspondant à la condition enfant que vous souhaitez supprimer.

Cette section décrit les conditions suivantes :

* [Et](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Not](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [OU](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## Et {#section-a14dba4b07cc4ab9aeb20868f773db7c}

Le [!DNL And] La condition peut comporter aucune ou plusieurs conditions enfants et renvoie true (vrai) lorsqu’aucun de ses noeuds enfants ne renvoie false (faux).

Le [!DNL And] condition forme l’opération racine de tous les tests de condition dans le serveur Data Workbench. Si la variable [!DNL And] La condition ne contient aucun enfant, la condition est évaluée comme vraie et l’opération associée se poursuit. C’est pourquoi les actions qui ont uniquement la variable [!DNL And] comme test de condition s’exécute toujours et pourquoi il est utilisé comme racine pour tous les tests de condition.

Cet exemple illustre comment une [!DNL And] est utilisée pour s’assurer que la variable [!DNL Copy] la transformation se produit uniquement lorsque la date de l’entrée du journal s’est produite en 2006 et que la page demandée a été [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## Not {#section-7e48b61266aa43ecbc48b979bf5e939b}

Le [!DNL Neither] La condition peut comporter aucune ou plusieurs conditions enfants et renvoie false si l’une de ses conditions enfants est vraie. Si la variable [!DNL Neither] La condition ne contient aucun enfant, aucun de ses enfants ne peut renvoyer la valeur true. Par conséquent, la variable [!DNL Neither] est évaluée sur true.

L’exemple suivant illustre une [!DNL Neither] condition avec deux [!DNL Range] ses conditions d&#39;enfant. Comme défini, la variable [!DNL Neither] La condition exclut les entrées de journal qui se sont produites entre le 1er janvier 2007 et le 10 janvier 2007 ou pendant la période du 12 janvier 2007 au 14 janvier 2007. Une telle condition peut être utilisée comme [!DNL Log Entry Condition] pour éliminer les transactions d’un jeu de données pendant les périodes où un problème connu se produisait avec les données collectées.

![](assets/cfg_Condition_NeitherCondition.png)

## OU {#section-a3aa0f56b6234f2680fa81939228326b}

Le [!DNL Or] La condition peut comporter aucune ou plusieurs conditions enfants et renvoie true (vrai) si au moins l’une de ses conditions enfants est vraie. Si la variable [!DNL Or] La condition ne contient aucun enfant, aucun de ses enfants ne peut renvoyer la valeur true. Par conséquent, la variable [!DNL Or] est évaluée sur false.

Cet exemple illustre la fonction [!DNL Or] avec une condition [!DNL String Match] condition et une [!DNL Range] la condition de ses enfants. Le [!DNL Or] la condition n’est satisfaite que si l’entrée de journal a la valeur [!DNL x-hasproblem] est définie sur oui ou l’entrée du journal s’est produite au cours de la période du 1er janvier 2007 au 10 janvier 2007.

![](assets/cfg_Condition_OrCondition.png)
