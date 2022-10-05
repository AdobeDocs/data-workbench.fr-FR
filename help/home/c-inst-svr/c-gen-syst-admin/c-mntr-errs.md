---
description: Pour détecter les erreurs système et applicatif le plus tôt possible et les corriger avant qu’elles ne provoquent des problèmes majeurs ou des pannes, vous devez régulièrement surveiller vos journaux d’événements.
title: Surveillance des erreurs dans les événements
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
exl-id: 88f48594-5c73-4ae3-8014-b8543e689426
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 6%

---

# Surveillance des erreurs dans les événements{#monitoring-events-for-errors}

{{eol}}

Pour détecter les erreurs système et applicatif le plus tôt possible et les corriger avant qu’elles ne provoquent des problèmes majeurs ou des pannes, vous devez régulièrement surveiller vos journaux d’événements.

**Fréquence recommandée :** Toutes les 5-10 minutes

Pour surveiller les produits logiciels de votre serveur d’Adobe, votre outil de gestion automatisée peut être défini de manière à surveiller votre journal d’événements afin de détecter les erreurs avec l’&quot;Adobe&quot; source, puis d’alerter le personnel approprié sur les problèmes qui peuvent nécessiter une intervention.

Sous Windows, les messages d’erreur relatifs à l’application sont générés dans le journal des événements d’application sous Windows, accessible à l’aide de la visionneuse d’événements Windows. Dans Unix, les messages d’erreur de l’application sont générés dans le syslog Unix à l’aide de la fonctionnalité LOG_DAEMON .

**Pour ouvrir la visionneuse d’événements Windows**

* Cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.
