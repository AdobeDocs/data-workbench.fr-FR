---
description: La nouvelle condition du visiteur est une opération de condition utilisée avec les données du site web pour déterminer les visiteurs qui sont considérés comme étant inclus dans le jeu de données.
title: Nouvelle condition de visiteur
uuid: e9733109-5bf3-47ce-974c-d68264291f19
exl-id: a0520edd-bde3-4f55-858c-8974d4224435
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 3%

---

# Nouvelle condition de visiteur{#new-visitor-condition}

La nouvelle condition du visiteur est une opération de condition utilisée avec les données du site web pour déterminer les visiteurs qui sont considérés comme étant inclus dans le jeu de données.

[!DNL New Visitor Condition] définit la première entrée de journal (triée par heure) d’un visiteur qui doit être utilisé dans le jeu de données, et toutes les entrées de journal suivantes de ce visiteur sont incluses dans le jeu de données, qu’elles respectent ou non cette condition. Étant donné que la fonction [!DNL New Visitor Condition] exige que les données soient triées par visiteur et par heure, elles ne sont appliquées que lors de la phase de transformation de la construction du jeu de données.

La valeur [!DNL New Visitor Condition] affichée dans cet exemple crée un jeu de données qui inclut uniquement ces entrées de journal pour les visiteurs qui répondent à des campagnes par e-mail. Pour ce faire, utilisez le test [!DNL NotEmptyCondition] (voir [Non vide](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)) et le champ [!DNL x-campaign-email] comme entrée de l’expression régulière. Une fois que les nouveaux visiteurs qui respectent la condition sont identifiés, toutes les entrées de journal de ces visiteurs sont capturées.

![](assets/cfg_Transformation_NewVisitorCondition.png)
