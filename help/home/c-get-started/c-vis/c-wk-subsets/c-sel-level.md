---
description: Lorsque vous créez un sous-ensemble, vous devez spécifier un niveau.
title: Sélectionner un niveau
uuid: 18c2bee7-a70f-4510-978f-830b56780f47
exl-id: 39d8407c-e2ec-4080-8918-26cafbf988df
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 4%

---

# Sélectionner un niveau{#select-a-level}

Lorsque vous créez un sous-ensemble, vous devez spécifier un niveau.

Un niveau est toute dimension dénombrable. Par exemple, si vous travaillez sur des données de site Web, si vous sélectionnez l’élément Type dans la dimension Jour de la semaine et créez un sous-ensemble, vous devez sélectionner le niveau à vue : Vue de page, session ou Visiteur.

* **Jour de la semaine=&quot;Identité&quot; par Vue de page :** Le niveau de vue de page vous montre uniquement les vues de page qui se sont produites un mardi.

   ![](assets/vis_Subset_byPageView.png)

* **Jour de la semaine=&quot;Date&quot; par session :** Le niveau de session vous montre uniquement les sessions qui se sont déroulées un mardi.

   ![](assets/vis_Subset_bySession.png)

* **Day of Week=&quot;Tue&quot; par Visiteur :** Le niveau visiteur vous montre tous les visiteurs qui sont venus sur le site le mardi, mais il montre aussi les autres jours où ces mêmes visiteurs sont venus sur le site.

   ![](assets/vis_Subset_byVisitor.png)
