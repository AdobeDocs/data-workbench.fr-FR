---
description: Informations sur l’état de votre serveur de rapports et sur celui de votre jeu de rapports.
title: Vérification du statut du rapport
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# Vérification du statut du rapport{#reviewing-report-status}

Informations sur l’état de votre serveur de rapports et sur celui de votre jeu de rapports.

* [État du serveur de rapports](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [État du jeu de rapports](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## État du serveur de rapports {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Fréquence recommandée :** uniquement si nécessaire

[!DNL Report] envoie des informations d’état au serveur Data Workbench toutes les deux minutes concernant l’état du  [!DNL Report] serveur. Ces informations sont visibles sous le noeud [!DNL Report Server Status] dans l’interface [!DNL Detailed Status].

**Pour ouvrir la  [!DNL Detailed Status] visualisation**

1. Dans Data Workbench, cliquez avec le bouton droit dans un espace de travail et cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. Dans l’interface [!DNL Servers], cliquez avec le bouton droit sur l’icône du serveur Data Workbench auquel la machine [!DNL Report] se connecte et cliquez sur **[!UICONTROL Detailed Status.]**

1. Cliquez sur **[!UICONTROL Report Server Status]**.

Si plusieurs [!DNL Report] sont connectés au serveur Data Workbench, une entrée s’affiche pour chaque [!DNL Report Server] dans le vecteur État. L’intervalle de deux minutes peut être remplacé en spécifiant une valeur dans le paramètre Intervalle d’état (secondes) dans le noeud [!DNL Reporting] du fichier [!DNL ReportServer.cfg] .

Pour plus d’informations sur le fichier [!DNL ReportServer.cfg], voir [Configuration du jeu de rapports](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0). Pour plus d’informations sur la configuration de [!DNL Report], voir [Installation du rapport](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Pour plus d’informations sur [!DNL Detailed Status], consultez le chapitre Interfaces d’administration du *Guide de l’utilisateur du Data Workbench*.

## État du jeu de rapports {#section-8569b94266b74a1f85d2a85106a2aaef}

**Fréquence recommandée :** uniquement si nécessaire

[!DNL Report] transmet les informations d’état de chaque jeu de rapports au serveur du Data Workbench. Les informations de base, telles que le moment où un jeu de rapports est généré et distribué, s’affichent dans Data Workbench au-dessus du jeu de rapports en texte vert. Lors de l’exécution des rapports, [!DNL Report] le serveur génère un message toutes les deux minutes indiquant le pourcentage de requêtes en cours terminées. Cet intervalle de deux minutes peut être remplacé en spécifiant une valeur dans le paramètre Intervalle de message d’achèvement (secondes) dans le noeud [!DNL Reporting] du fichier [!DNL ReportServer.cfg] .

![](assets/report_status.png)

>[!NOTE]
>
>Si une erreur s’est produite lors de l’exécution d’un rapport, elle est indiquée en rouge sous la miniature de ce rapport. Vous pouvez cliquer avec le bouton droit sur l’espace de travail pour afficher le message d’erreur complet.
