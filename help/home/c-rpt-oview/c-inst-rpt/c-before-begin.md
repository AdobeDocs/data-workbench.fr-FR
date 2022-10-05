---
description: Pour que certaines fonctionnalités du serveur de rapports fonctionnent, vous devez fournir et configurer du matériel ou des logiciels avant l’installation.
title: Avant de commencer
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
exl-id: 5c8bb4c3-fe76-4b4e-960d-113a9927ad59
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 1%

---

# Avant de commencer{#before-you-begin}

{{eol}}

Pour que certaines fonctionnalités du serveur de rapports fonctionnent, vous devez fournir et configurer du matériel ou des logiciels avant l’installation.

## Exigences de base du serveur de rapports {#section-e891eaee79fe4fa98e658426dc3b2777}

Les rapports qui sont générés peuvent prendre la forme d’images .PNG ou de feuilles de calcul .XLS placées dans un système de fichiers ou sous la forme d’emails. Les exigences matérielles sont identiques à celles du scénario [client de Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements).

La configuration requise pour le serveur de rapports est la suivante :

* Accès au système de fichiers pour la sortie des données (partage réseau ou lecteur local).
* Accès au serveur SMTP configuré.
* Microsoft Excel 2010 64 bits ou version ultérieure installé sur [!DNL Report] Serveur. Voir [Considérations relatives à l’automatisation côté serveur d’Office](https://support.microsoft.com/kb/257757) pour plus d’informations.

## Conditions supplémentaires {#section-f53d4388656a4dfc90aefe29dfabef89}

* **Installez un adaptateur graphique approprié.** Pour générer correctement les rapports, la machine sur laquelle vous installez [!DNL Report] Un adaptateur graphique approprié doit être installé sur le serveur.

* **Installez Microsoft Excel pour générer les rapports sous forme de fichiers Excel.** Pour générer et distribuer des rapports sous la forme de fichiers Excel Microsoft ( [!DNL .xls] ou [!DNL .xlsx]), la version appropriée de Microsoft Excel 64 bits doit être installée et enregistrée sur l’ordinateur sur lequel vous installez le serveur de rapports. Si Excel n’a pas été enregistré et que le serveur de rapports tente d’y accéder pour la première fois, une boîte de dialogue d’enregistrement s’affiche. Si vous ne savez pas si la copie est enregistrée, démarrez Excel manuellement et si une boîte de dialogue d’enregistrement s’affiche, exécutez le processus d’enregistrement.

   >[!NOTE]
   >
   >Lorsque vous générez des rapports sous la forme de fichiers Excel, vous ouvrez une nouvelle instance d’Excel. Pour plus d’informations sur ce processus, voir [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).

* **Accédez à un serveur SMTP pour distribuer les rapports par email.** Si vous souhaitez distribuer des rapports par email, le serveur de rapports doit pouvoir se connecter à un serveur SMTP et les ports appropriés au service de transfert de courrier électronique doivent être ouverts.
