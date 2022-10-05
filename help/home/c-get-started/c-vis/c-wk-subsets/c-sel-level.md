---
description: Lorsque vous créez un sous-ensemble, vous devez spécifier un niveau.
title: Sélectionner un niveau
uuid: 18c2bee7-a70f-4510-978f-830b56780f47
exl-id: 39d8407c-e2ec-4080-8918-26cafbf988df
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 4%

---

# Sélectionner un niveau{#select-a-level}

{{eol}}

Lorsque vous créez un sous-ensemble, vous devez spécifier un niveau.

Un niveau est toute dimension dénombrable. Par exemple, si vous utilisez des données de site web, si vous sélectionnez l’élément Type dans la dimension Jour de la semaine et créez un sous-ensemble, vous devez sélectionner le niveau que vous souhaitez afficher : Page vue, Session ou Visiteur.

* **Jour de la semaine=&quot;Mode&quot; par page vue :** Le niveau des pages vues vous montre uniquement les pages vues qui se sont produites un mardi.

   ![](assets/vis_Subset_byPageView.png)

* **Jour de la semaine=&quot;Mode&quot; par session :** Le niveau de session affiche uniquement les sessions qui se sont produites un mardi.

   ![](assets/vis_Subset_bySession.png)

* **Jour de la semaine=&quot;Mode&quot; par visiteur :** Le niveau du visiteur indique tous les visiteurs qui sont venus sur le site le mardi, mais il indique également les autres jours où ces mêmes visiteurs sont venus sur le site.

   ![](assets/vis_Subset_byVisitor.png)
