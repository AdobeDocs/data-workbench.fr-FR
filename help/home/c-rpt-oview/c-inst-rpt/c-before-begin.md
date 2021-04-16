---
description: Pour que certaines fonctionnalités du serveur de rapports fonctionnent, vous devez fournir et configurer du matériel ou des logiciels avant de procéder à l’installation.
title: Avant de commencer
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
exl-id: 5c8bb4c3-fe76-4b4e-960d-113a9927ad59
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 1%

---

# Avant de commencer{#before-you-begin}

Pour que certaines fonctionnalités du serveur de rapports fonctionnent, vous devez fournir et configurer du matériel ou des logiciels avant de procéder à l’installation.

## Configuration requise de base pour le serveur de rapports {#section-e891eaee79fe4fa98e658426dc3b2777}

Les rapports qui sont générés peuvent prendre la forme d’images .PNG ou de feuilles de calcul .XLS placées dans un système de fichiers ou sous forme de courriers électroniques. La configuration matérielle requise est identique au [client de l&#39;outil de données](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements).

Les exigences suivantes s’appliquent au serveur de rapports :

* Accès au système de fichiers pour la sortie des données (partage réseau ou lecteur local).
* Accès au serveur SMTP configuré.
* Microsoft Excel 2010 64 bits ou version ultérieure installé sur [!DNL Report] serveur. Voir [Considérations relatives à l&#39;automatisation côté serveur d&#39;Office](http://support.microsoft.com/kb/257757) pour plus d&#39;informations.

## Autres exigences {#section-f53d4388656a4dfc90aefe29dfabef89}

* **Installez un adaptateur graphique approprié.** Pour générer correctement les rapports, l&#39;ordinateur sur lequel vous installez  [!DNL Report] le serveur doit disposer d&#39;une carte graphique appropriée.

* **Installez Microsoft Excel pour générer des rapports sous forme de fichiers Excel.** Pour générer et distribuer des rapports sous la forme de fichiers Microsoft Excel (  [!DNL .xls] ou  [!DNL .xlsx]), la version 64 bits de Microsoft Excel installée et enregistrée sur l’ordinateur sur lequel vous installez Report Server doit être la version appropriée de Microsoft Excel. Si Excel n’a pas été enregistré et que Report Server tente d’y accéder pour la première fois, Excel affiche une boîte de dialogue d’enregistrement. Si vous ne savez pas si la copie est enregistrée, début Excel manuellement et si une boîte de dialogue d&#39;enregistrement s&#39;affiche, effectuez le processus d&#39;enregistrement.

   >[!NOTE]
   >
   >Lorsque vous générez des rapports sous la forme de fichiers Excel, vous ouvrez une nouvelle instance d&#39;Excel. Pour plus d’informations sur ce processus, voir [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).

* **Fournissez l’accès à un serveur SMTP pour distribuer les rapports par courriel.** Si vous souhaitez distribuer des rapports par courrier électronique, Report Server doit être en mesure de se connecter à un serveur SMTP et les ports appropriés au service de transfert de courrier électronique doivent être ouverts.
