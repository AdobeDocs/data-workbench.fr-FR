---
description: La nouvelle condition du visiteur est une opération de condition utilisée avec les données du site Web pour déterminer les visiteurs qui sont considérés comme pouvant être inclus dans le jeu de données.
solution: Analytics
title: Nouvelle condition du visiteur
topic: Data workbench
uuid: e9733109-5bf3-47ce-974c-d68264291f19
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Nouvelle condition du visiteur{#new-visitor-condition}

La nouvelle condition du visiteur est une opération de condition utilisée avec les données du site Web pour déterminer les visiteurs qui sont considérés comme pouvant être inclus dans le jeu de données.

Le [!DNL New Visitor Condition] définit la première entrée de journal (triée par heure) d’un visiteur à utiliser dans le jeu de données et toutes les entrées de journal suivantes de ce visiteur sont incluses dans le jeu de données, qu’elles respectent ou non cette condition. Comme les données [!DNL New Visitor Condition] doivent être classées par visiteur et par heure, elles ne sont appliquées que pendant la phase de transformation de la construction du jeu de données.

L’ [!DNL New Visitor Condition] exemple ci-dessous crée un jeu de données qui inclut uniquement les entrées de journal des visiteurs qui répondent aux campagnes par courrier électronique. Pour ce faire, utilisez le [!DNL NotEmptyCondition] test (voir [Pas vide](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)) et le champ [!DNL x-campaign-email] comme entrée à l’expression régulière. Une fois que les nouveaux visiteurs qui remplissent la condition sont identifiés, toutes les entrées du journal de ces visiteurs sont capturées.

![](assets/cfg_Transformation_NewVisitorCondition.png)

