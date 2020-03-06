---
description: Le produit du tableau de bord requiert une licence fournie par Adobe ClientCare.
solution: Analytics
title: Ajouter la clé de licence du tableau de bord
topic: Data workbench
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ajouter la clé de licence du tableau de bord{#add-dashboard-license-key}

Le produit du tableau de bord requiert une licence fournie par Adobe ClientCare.

1. Open **[!UICONTROL SQL Management Studio]** as an Administrator.
1. Ouvrez la base de données créée par le tableau de bord (par exemple, thinclientdb).
1. Cliquez avec le bouton droit de la souris sur le **[!UICONTROL Configuration]** tableau et cliquez sur **[!UICONTROL Edit Top 200 Rows]**.
1. Recherchez le **[!UICONTROL licenseKey]** champ et saisissez la clé fournie par Adobe ClientCare dans la **[!UICONTROL Value]** colonne.
1. Redémarrez le **[!UICONTROL Application Pool]** dans le **[!UICONTROL IIS Manager Console]**.
