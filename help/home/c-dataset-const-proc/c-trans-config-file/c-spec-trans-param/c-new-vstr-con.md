---
description: La nouvelle condition du visiteur est une opération de condition utilisée avec les données du site web pour déterminer les visiteurs qui sont considérés comme étant inclus dans le jeu de données.
title: Nouvelle condition de visiteur
uuid: e9733109-5bf3-47ce-974c-d68264291f19
exl-id: a0520edd-bde3-4f55-858c-8974d4224435
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 3%

---

# Nouvelle condition de visiteur{#new-visitor-condition}

{{eol}}

La nouvelle condition du visiteur est une opération de condition utilisée avec les données du site web pour déterminer les visiteurs qui sont considérés comme étant inclus dans le jeu de données.

Le [!DNL New Visitor Condition] définit la première entrée de journal (ordonnée par le temps) d’un visiteur qui doit être utilisé dans le jeu de données, et toutes les entrées de journal suivantes de ce visiteur sont incluses dans le jeu de données, qu’elles respectent ou non cette condition. Parce que la variable [!DNL New Visitor Condition] exige que les données soient classées par visiteur et par heure ; elles ne sont appliquées que lors de la phase de transformation de la construction du jeu de données.

Le [!DNL New Visitor Condition] illustré dans cet exemple crée un jeu de données qui inclut uniquement ces entrées de journal pour les visiteurs qui répondent à des campagnes par e-mail. Pour ce faire, utilisez la méthode [!DNL NotEmptyCondition] test (voir [Non vide](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)) et la variable [!DNL x-campaign-email] comme entrée de l’expression régulière. Une fois que les nouveaux visiteurs qui respectent la condition sont identifiés, toutes les entrées de journal de ces visiteurs sont capturées.

![](assets/cfg_Transformation_NewVisitorCondition.png)
