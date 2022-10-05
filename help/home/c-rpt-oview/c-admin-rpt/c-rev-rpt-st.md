---
description: Informations sur votre état de serveur de rapports et sur le statut de votre jeu de rapports.
title: Vérification du statut du rapport
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# Vérification du statut du rapport{#reviewing-report-status}

{{eol}}

Informations sur votre état de serveur de rapports et sur le statut de votre jeu de rapports.

* [État du serveur de rapports](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [État du jeu de rapports](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## État du serveur de rapports {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Fréquence recommandée :** Lorsque cela est nécessaire

[!DNL Report] envoie des informations d’état au serveur Data Workbench toutes les deux minutes concernant l’état de la variable [!DNL Report] Serveur. Ces informations sont visibles sous la variable [!DNL Report Server Status] dans le noeud [!DNL Detailed Status] .

**Pour ouvrir la [!DNL Detailed Status] visualisation**

1. Dans Data Workbench, cliquez avec le bouton droit dans un espace de travail, puis cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. Dans le [!DNL Servers] , cliquez avec le bouton droit de la souris sur l’icône du serveur Data Workbench qui affiche [!DNL Report] La machine se connecte et clique sur **[!UICONTROL Detailed Status.]**

1. Cliquez sur **[!UICONTROL Report Server Status]**.

Si plus d’un [!DNL Report] est connecté au serveur Data Workbench, une entrée s’affiche pour chaque [!DNL Report Server] dans le vecteur Status (État). L’intervalle de deux minutes peut être remplacé en spécifiant une valeur dans le paramètre Intervalle d’état (secondes) dans la variable [!DNL Reporting] du noeud [!DNL ReportServer.cfg] fichier .

Pour plus d’informations sur la variable [!DNL ReportServer.cfg] fichier, voir [Configuration du jeu de rapports](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0). Pour plus d’informations sur la configuration [!DNL Report], voir [Installation du rapport](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Pour plus d’informations sur [!DNL Detailed Status], voir le chapitre Interfaces administratives de la section *Guide de l’utilisateur de Data Workbench*.

## État du jeu de rapports {#section-8569b94266b74a1f85d2a85106a2aaef}

**Fréquence recommandée :** Lorsque cela est nécessaire

[!DNL Report] transmet les informations d’état de chaque jeu de rapports au serveur du Data Workbench. Les informations de base, telles que le moment où un jeu de rapports est généré et distribué, s’affichent dans Data Workbench au-dessus du jeu de rapports en texte vert. Lors de l’exécution de rapports, [!DNL Report] Le serveur génère un message toutes les deux minutes indiquant le pourcentage de requêtes en cours terminées. Cet intervalle de deux minutes peut être remplacé en spécifiant une valeur dans le paramètre Intervalle de message d’achèvement (secondes) de la variable [!DNL Reporting] du noeud [!DNL ReportServer.cfg] fichier .

![](assets/report_status.png)

>[!NOTE]
>
>Si une erreur s’est produite lors de l’exécution d’un rapport, elle est indiquée en rouge sous la miniature de ce rapport. Vous pouvez cliquer avec le bouton droit sur l’espace de travail pour afficher le message d’erreur complet.
