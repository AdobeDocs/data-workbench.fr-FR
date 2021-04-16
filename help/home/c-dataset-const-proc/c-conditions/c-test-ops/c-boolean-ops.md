---
description: Les opérations booléennes combinent les résultats des opérations de test, qui fonctionnent comme des enfants des opérations booléennes.
title: Opérations booléennes
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# Opérations booléennes{#boolean-operations}

Les opérations booléennes combinent les résultats des opérations de test, qui fonctionnent comme des enfants des opérations booléennes.

Pour plus d’informations sur les opérations de test, voir [Opérations de test](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). Lorsque vous définissez une opération [!DNL boolean], vous pouvez définir zéro ou plusieurs enfants pour l&#39;opération.

**Pour ajouter une condition enfant à une opération booléenne**

1. Cliquez avec le bouton droit de la souris sur le nom ou le numéro correspondant à l&#39;opération [!DNL Boolean].
1. Cliquez sur **[!UICONTROL Add new child]** et choisissez l’un des types de condition disponibles à ajouter.
1. Répétez les étapes 1 et 2 jusqu’à ce que vous ayez ajouté toutes les conditions enfants souhaitées pour l’opération [!DNL Boolean].

   >[!NOTE]
   >
   >Lorsque vous cliquez avec le bouton droit sur le nom ou le numéro correspondant à une opération [!DNL Boolean], l&#39;option de menu [!DNL Add new sibling] s&#39;affiche. Un frère est une autre condition à la même position relative dans la hiérarchie de conditions que l&#39;opération [!DNL Boolean] sur laquelle vous avez cliqué avec le bouton droit de la souris. Ajouter un nouveau frère pour une opération [!DNL Boolean] revient à ajouter une nouvelle condition en cliquant avec le bouton droit de la souris sur le paramètre [!DNL Condition] ou [!DNL Log Entry Condition].

**Pour supprimer une condition enfant d&#39;une opération booléenne :**

1. Cliquez avec le bouton droit sur le nom de la condition enfant ou sur le numéro correspondant à la condition enfant que vous souhaitez supprimer de l&#39;opération [!DNL Boolean].
1. Cliquez sur **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, où nombre correspond au numéro correspondant à la condition enfant que vous souhaitez supprimer.

Cette section traite des conditions suivantes :

* [And](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Not](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [OU](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## Et {#section-a14dba4b07cc4ab9aeb20868f773db7c}

La condition [!DNL And] peut avoir zéro ou plusieurs conditions enfant et renvoie true si aucun de ses noeuds enfants ne renvoie false.

La condition [!DNL And] forme l’opération racine de tous les tests de condition dans le serveur de l’outil de données. Si la condition [!DNL And] ne contient aucun enfant, elle est évaluée sur true et l’opération associée se poursuit. C’est pourquoi les actions qui n’ont que la condition [!DNL And] comme test de condition s’exécutent toujours et pourquoi elle est utilisée comme racine pour tous les tests de condition.

Cet exemple montre comment une condition [!DNL And] est utilisée pour s&#39;assurer que la transformation [!DNL Copy] se produit uniquement lorsque la date de l&#39;entrée de journal a été saisie en 2006 et que la page demandée était [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## Ni {#section-7e48b61266aa43ecbc48b979bf5e939b}

La condition [!DNL Neither] peut avoir zéro ou plusieurs conditions enfant et renvoie false si l’une de ses conditions enfant est vraie. Si la condition [!DNL Neither] ne contient aucun enfant, aucun de ses enfants ne peut renvoyer la valeur true. Par conséquent, la condition [!DNL Neither] est évaluée sur true.

L&#39;exemple suivant montre une condition [!DNL Neither] avec deux conditions [!DNL Range] comme enfants. Comme défini, la condition [!DNL Neither] exclut les entrées de journal qui se sont produites entre le 1er janvier 2007 et le 10 janvier 2007 ou entre le 12 janvier 2007 et le 14 janvier 2007. Une telle condition peut être utilisée en tant que [!DNL Log Entry Condition] pour éliminer les transactions d&#39;un jeu de données pendant les périodes où un problème connu se produisait avec les données collectées.

![](assets/cfg_Condition_NeitherCondition.png)

## OU {#section-a3aa0f56b6234f2680fa81939228326b}

La condition [!DNL Or] peut avoir zéro ou plusieurs conditions enfant et renvoie true si au moins l’une de ses conditions enfant est vraie. Si la condition [!DNL Or] ne contient aucun enfant, aucun de ses enfants ne peut renvoyer la valeur true. Par conséquent, la condition [!DNL Or] est évaluée sur false.

Cet exemple montre la condition [!DNL Or] avec une condition [!DNL String Match] et une condition [!DNL Range] comme enfants. La condition [!DNL Or] n&#39;est satisfaite que si la valeur [!DNL x-hasproblem] de l&#39;entrée de journal est définie sur yes ou si l&#39;entrée de journal s&#39;est produite au cours de la période allant du 1er janvier 2007 au 10 janvier 2007.

![](assets/cfg_Condition_OrCondition.png)
