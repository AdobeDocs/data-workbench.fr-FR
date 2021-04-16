---
description: Vous pouvez visualiser les données de plusieurs profils en un seul tableau de bord.
title: Sélections sur plusieurs profils
uuid: e9377bcf-8de9-4952-a81a-863216f25fb7
exl-id: a14400bf-64e3-44be-b9ab-d8a9ded406ae
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 2%

---

# Sélections sur plusieurs profils{#cross-profile-selections}

Vous pouvez visualiser les données de plusieurs profils en un seul tableau de bord.

Dans certains cas, les sélections d’une visualisation peuvent également être appliquées aux visualisations d’un autre profil. Par exemple, si vous créez des visualisations à partir d’un profil **[!UICONTROL Call Center]**et d’un profil **[!UICONTROL Website Traffic]** sur un tableau de bord, vous pouvez sélectionner un mois de cible pour que les données de toutes les visualisations soient segmentées simultanément sur ce mois, même si les jeux de données sont entièrement différents.

Lorsque des visualisations de plusieurs profils existent dans un tableau de bord, vous pouvez effectuer une sélection dans une visualisation si la dimension de cette visualisation existe également sur tous les autres profils représentés à l’écran. Cependant, les sélections seront désactivées si aucune dimension n’est trouvée globalement dans toutes les autres visualisations à l’écran et que les utilisateurs verront un message **[!UICONTROL Selections Disabled]**.

![](assets/selection_disabled.png)

>[!NOTE]
>
>Même si les dimensions peuvent porter le même nom sur plusieurs profils, elles peuvent ne pas avoir la même signification. Il est important d’étudier chaque dimension afin de déterminer s’il est approprié de l’utiliser pour effectuer des sélections sur plusieurs profils.
