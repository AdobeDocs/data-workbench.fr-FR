---
description: Les sélections dans une ou plusieurs visualisations d’un tableau de bord peuvent être verrouillées afin de conserver les sélections actuelles et d’éviter toute autre modification.
title: Sélections verrouillées
uuid: 0466baa1-6ffb-4b7b-8dc6-118de97c8549
exl-id: eaffe761-b2ac-4521-85ca-2c5227da3445
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 1%

---

# Sélections verrouillées{#locked-selections}

Les sélections dans une ou plusieurs visualisations d’un tableau de bord peuvent être verrouillées afin de conserver les sélections actuelles et d’éviter toute autre modification.

Le verrouillage des visualisations est utile pour guider l’analyse, car certains éléments peuvent être présélectionnés et appliqués de manière permanente à l’ensemble du tableau de bord. Ceci fournit un indicateur visuel à l’écran de ce qui est filtré sans permettre de le modifier.

Le verrouillage s’avère également utile pour guider l’analyse en permettant uniquement aux utilisateurs de sélectionner des visualisations pertinentes pour l’analyse que le tableau de bord vise à réaliser. Par exemple, dans l’exemple de tableau de bord ci-dessous, l’exploration jusqu’au niveau du code postal peut aller au-delà de l’analyse du volume d’appels de haut niveau. Dans ce cas, il peut être logique que la table **[!UICONTROL Metric Breakdown by Zip]** soit verrouillée et que les sélections ne soient autorisées que dans les visualisations Mois, Jour de la semaine et Datacenter.

Si vous essayez d’effectuer des sélections sur une visualisation verrouillée, un message s’affiche pour vous informer que la visualisation est verrouillée. Une icône de verrou doré apparaît également dans l’en-tête de visualisation lorsque le curseur de la souris survole la visualisation verrouillée.

![](assets/selection_locked.png)

Comme pour toute sélection, les sélections verrouillées sont conservées lors de l’enregistrement d’un tableau de bord et restent principales lors du chargement d’un tableau de bord. Pour plus d’informations, voir [Verrouillage et déverrouillage des visualisations](../../../home/c-adobe-data-workbench-dashboard/c-visualizations/c-manipulating-visualizations/c-locking-and-unlocking-visualizations.md#concept-9215bcdd5bb44dee8d92ef0cc82f44d2).
