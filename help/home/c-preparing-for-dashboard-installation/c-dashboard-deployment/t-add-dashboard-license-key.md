---
description: Le produit tableau de bord nécessite une licence fournie par Adobe ClientCare.
title: Ajout de la clé de licence au tableau de bord
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
exl-id: bf532fb0-9287-4c15-aa4c-07f7bd0fdba7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 12%

---

# Ajout de la clé de licence au tableau de bord{#add-dashboard-license-key}

Le produit tableau de bord nécessite une licence fournie par Adobe ClientCare.

1. Ouvrez **[!UICONTROL SQL Management Studio]** en tant qu&#39;administrateur.
1. Ouvrez la base de données créée par tableau de bord (par exemple, thinclientdb).
1. Cliquez avec le bouton droit de la souris sur le tableau **[!UICONTROL Configuration]** et cliquez sur **[!UICONTROL Edit Top 200 Rows]**.
1. Recherchez le champ **[!UICONTROL licenseKey]** et saisissez la clé fournie par Adobe ClientCare dans la colonne **[!UICONTROL Value]**.
1. Redémarrez le **[!UICONTROL Application Pool]** dans le **[!UICONTROL IIS Manager Console]**.
