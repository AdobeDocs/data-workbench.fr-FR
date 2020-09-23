---
description: Vérifiez si l'émetteur s'exécute en configurant des alertes, en vérifiant l'état du système du capteur, etc.
solution: Analytics
title: Confirmation que l’émetteur de données est en cours d’exécution
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---


# Confirmation que l’émetteur de données est en cours d’exécution{#confirming-that-the-data-transmitter-is-running}

Vérifiez si l&#39;émetteur s&#39;exécute en configurant des alertes, en vérifiant l&#39;état du système du capteur, etc.

**Fréquence recommandée :** Toutes les 5 à 10 minutes

* [Vérifiez que le processus de l’émetteur est en cours d’exécution.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Configurez des alertes administratives dans Insight Server.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Vérifiez l&#39;état du système du capteur.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Vérification du processus d&#39;émetteur {#section-79806fa3b7034a8eaf571a66e24874d7}

L’une des manières de vérifier l’exécution de l’émetteur consiste à vérifier que le processus de l’ [!DNL Sensor] émetteur s’exécute sur chaque serveur Web sur lequel une [!DNL Sensor] instance est installée. Le processus d’émetteur apparaît sous la forme &quot;txlogd&quot; dans la liste des processus du serveur Web. Vous pouvez effectuer cette vérification à l&#39;aide d&#39;un outil de surveillance du système.

## Configuration des alertes d&#39;administration sur le serveur Data Workbench {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Une autre façon de vérifier que l’émetteur est en cours d’exécution consiste à configurer des alertes administratives automatisées dans le [!DNL data workbench server]. Lorsque des alertes d&#39;administration ont été configurées, l&#39; [!DNL data workbench server] utilisateur génère une alerte par courrier électronique lorsqu&#39;il n&#39;a reçu aucune donnée d&#39;un utilisateur configuré et précédemment connecté [!DNL Sensor] au cours de la période spécifiée dans le paramètre [!DNL Sensor] Délai d&#39;attente d&#39;alerte (min) du [!DNL data workbench server’s][!DNL Administrative Alerts.cfg] fichier. Pour plus d&#39;informations sur la configuration des alertes administratives, consultez le Guide *d&#39;installation et d&#39;administration des produits* serveur.

## Vérification de l&#39;état du système du capteur {#section-de9d7e359242487a9fbead4ed65aebbc}

Une autre façon de vérifier que l&#39;émetteur est en cours d&#39;exécution consiste à vérifier manuellement le [!DNL Servers Manager] Data Workbench.

**Pour vue à la variable[!DNL Servers Manager]**

* Dans le Data Workbench, cliquez avec le bouton droit de la souris dans un espace de travail, cliquez sur **[!UICONTROL Admin]**, puis sous [!DNL Manage], cliquez sur **[!UICONTROL Servers]**.

Si l&#39;icône d&#39;un [!DNL Sensor] est verte, l&#39;émetteur est en cours d&#39;exécution.

Pour plus d’informations sur le [!DNL Servers Manager]guide, voir le chapitre Interfaces d’administration du *Guide[!DNL Sensor]du* Data Workbench.
