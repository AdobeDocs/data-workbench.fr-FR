---
description: Pour détecter les erreurs système et d’application le plus tôt possible et les corriger avant qu’elles ne provoquent des problèmes majeurs ou des pannes, vous devez régulièrement surveiller vos journaux d’événements.
solution: Insight
title: Contrôle des événements pour les erreurs
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Contrôle des événements pour les erreurs{#monitoring-events-for-errors}

Pour détecter les erreurs système et d’application le plus tôt possible et les corriger avant qu’elles ne provoquent des problèmes majeurs ou des pannes, vous devez régulièrement surveiller vos journaux d’événements.

**Fréquence recommandée :** Toutes les 5 à 10 minutes

Pour surveiller les produits logiciels de votre serveur Adobe, votre outil de gestion automatisée peut être configuré pour surveiller votre journal des événements afin de détecter les erreurs avec la source &quot;Adobe&quot;, puis pour avertir le personnel approprié des problèmes qui peuvent nécessiter une intervention.

Sous Windows, les messages d’erreur de l’application sont générés dans le journal des événements de l’application sous Windows, auquel vous pouvez accéder à l’aide de l’Observateur d’événements Windows. Dans Unix, les messages d&#39;erreur de l&#39;application sont générés dans le syslog Unix à l&#39;aide de la fonctionnalité LOG_DAEMON.

**Pour ouvrir l’Observateur d’événements Windows**

* Cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

