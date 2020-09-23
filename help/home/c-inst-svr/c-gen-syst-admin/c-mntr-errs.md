---
description: Pour détecter les erreurs système et d'application le plus rapidement possible et les corriger avant qu'elles ne provoquent des problèmes majeurs ou des pannes, vous devez régulièrement surveiller vos journaux de événement.
solution: Analytics
title: Surveillance des erreurs dans les événements
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 6%

---


# Surveillance des erreurs dans les événements{#monitoring-events-for-errors}

Pour détecter les erreurs système et d&#39;application le plus rapidement possible et les corriger avant qu&#39;elles ne provoquent des problèmes majeurs ou des pannes, vous devez régulièrement surveiller vos journaux de événement.

**Fréquence recommandée :** Toutes les 5 à 10 minutes

Pour surveiller les produits logiciels de votre serveur d&#39;Adobe, votre outil de gestion automatisée peut être configuré pour surveiller votre journal de événement à la recherche d&#39;erreurs avec l&#39;&quot;Adobe&quot; source, puis avertir le personnel approprié des problèmes qui pourraient nécessiter une intervention.

Sous Windows, les messages d’erreur relatifs à l’application sont générés dans le Journal des Événements de l’application sous Windows, accessible à l’aide de Windows Événement Viewer. Dans Unix, les messages d&#39;erreur de l&#39;application sont envoyés au syslog Unix à l&#39;aide de la fonction LOG_DAEMON.

**Pour ouvrir le lecteur de Événement Windows**

* Cliquez sur **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

