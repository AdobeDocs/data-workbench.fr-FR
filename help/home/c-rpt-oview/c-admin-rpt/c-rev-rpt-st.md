---
description: Informations sur l’état de votre serveur de rapports et de votre jeu de rapports.
solution: Analytics
title: Vérification de l’état du rapport
topic: Data workbench
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Vérification de l’état du rapport{#reviewing-report-status}

Informations sur l’état de votre serveur de rapports et de votre jeu de rapports.

* [État du serveur de rapports](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [État du jeu de rapports](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## État du serveur de rapports {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Fréquence recommandée :** Uniquement si nécessaire

[!DNL Report] envoie des informations d’état au serveur de l’outil de données toutes les deux minutes concernant l’état du [!DNL Report] serveur. Ces informations sont visibles sous le [!DNL Report Server Status] noeud de l’ [!DNL Detailed Status] interface.

**Pour ouvrir la[!DNL Detailed Status]visualisation**

1. Dans les outils de données, cliquez avec le bouton droit de la souris dans un espace de travail et cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. Dans l’ [!DNL Servers] interface, cliquez avec le bouton droit de la souris sur l’icône du serveur de l’outil de données auquel l’ [!DNL Report] ordinateur se connecte, puis cliquez sur **[!UICONTROL Detailed Status.]**

1. Cliquez sur **[!UICONTROL Report Server Status]**.

Si plusieurs [!DNL Report] sont connectées au serveur de l’outil de données, une entrée s’affiche pour chaque [!DNL Report Server] élément dans le vecteur État. L’intervalle de deux minutes peut être remplacé en spécifiant une valeur dans le paramètre Intervalle d’état (secondes) dans le [!DNL Reporting] noeud du [!DNL ReportServer.cfg] fichier.

Pour plus d’informations sur le [!DNL ReportServer.cfg] fichier, voir [Configuration du jeu](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)de rapports. Pour plus d’informations sur la configuration [!DNL Report], voir [Installation du rapport](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Pour plus d’informations sur [!DNL Detailed Status]les interfaces d’administration, consultez le chapitre Interfaces d’administration du Guide *de l’utilisateur des outils de* données.

## État du jeu de rapports {#section-8569b94266b74a1f85d2a85106a2aaef}

**Fréquence recommandée :** Uniquement si nécessaire

[!DNL Report] transmet les informations d’état de chaque jeu de rapports au serveur Outils de données. Les informations de base, comme lorsqu’un jeu de rapports est généré et où il est distribué, s’affichent dans les outils de données au-dessus du jeu de rapports en texte vert. Lors de l’exécution des rapports, [!DNL Report] le serveur génère un message toutes les deux minutes indiquant le pourcentage de requêtes en cours terminées. Cet intervalle de deux minutes peut être remplacé en spécifiant une valeur dans le paramètre Intervalle de message d’achèvement (secondes) dans le [!DNL Reporting] noeud du [!DNL ReportServer.cfg] fichier.

![](assets/report_status.png)

>[!NOTE]
>
>Si une erreur s&#39;est produite lors de l&#39;exécution d&#39;un rapport, l&#39;erreur est indiquée en rouge sous la miniature de ce rapport. Vous pouvez cliquer avec le bouton droit sur l’espace de travail pour afficher le message d’erreur complet.

