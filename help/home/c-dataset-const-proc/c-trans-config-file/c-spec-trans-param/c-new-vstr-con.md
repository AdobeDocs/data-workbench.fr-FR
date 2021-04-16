---
description: La nouvelle condition du Visiteur est une opération de condition utilisée avec les données du site Web pour déterminer quels visiteurs sont considérés pour inclusion dans le jeu de données.
title: Nouvelle condition de visiteur
uuid: e9733109-5bf3-47ce-974c-d68264291f19
exl-id: a0520edd-bde3-4f55-858c-8974d4224435
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 3%

---

# Nouvelle condition de visiteur{#new-visitor-condition}

La nouvelle condition du Visiteur est une opération de condition utilisée avec les données du site Web pour déterminer quels visiteurs sont considérés pour inclusion dans le jeu de données.

[!DNL New Visitor Condition] définit la première entrée de journal (triée par temps) pour un visiteur à utiliser dans le jeu de données et toutes les entrées de journal suivantes pour ce visiteur sont incluses dans le jeu de données, qu&#39;elles respectent ou non cette condition. Comme [!DNL New Visitor Condition] exige que les données soient triées par visiteur et par temps, elles ne sont appliquées que pendant la phase de transformation de la construction du jeu de données.

Le [!DNL New Visitor Condition] illustré dans cet exemple crée un jeu de données qui inclut uniquement les entrées de journal des visiteurs qui répondent aux campagnes par courrier électronique. Pour ce faire, il faut utiliser le test [!DNL NotEmptyCondition] (voir [Non vide](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)) et le champ [!DNL x-campaign-email] comme entrée à l&#39;expression normale. Une fois que les nouveaux visiteurs qui remplissent la condition sont identifiés, toutes les entrées de journal de ces visiteurs sont capturées.

![](assets/cfg_Transformation_NewVisitorCondition.png)
