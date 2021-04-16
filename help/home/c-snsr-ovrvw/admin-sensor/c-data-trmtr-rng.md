---
description: Vérifiez si l'émetteur s'exécute en configurant des alertes, en vérifiant l'état du système du capteur, etc.
title: Confirmation que l’émetteur de données est en cours d’exécution
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---

# Confirmation que l’émetteur de données est en cours d’exécution{#confirming-that-the-data-transmitter-is-running}

Vérifiez si l&#39;émetteur s&#39;exécute en configurant des alertes, en vérifiant l&#39;état du système du capteur, etc.

**Fréquence recommandée :** toutes les 5 à 10 minutes

* [Vérifiez que le processus de l’émetteur est en cours d’exécution.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Configurez des alertes administratives dans Insight Server.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Vérifiez l&#39;état du système du capteur.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Vérification du processus d&#39;émetteur {#section-79806fa3b7034a8eaf571a66e24874d7}

Pour vérifier que l&#39;émetteur est en cours d&#39;exécution, vous pouvez vérifier que le processus d&#39;émetteur [!DNL Sensor] est en cours d&#39;exécution sur chaque serveur Web sur lequel une instance [!DNL Sensor] est installée. Le processus d’émetteur apparaît sous la forme &quot;txlogd&quot; dans la liste des processus du serveur Web. Vous pouvez effectuer cette vérification à l&#39;aide d&#39;un outil de surveillance du système.

## Configuration des alertes d&#39;administration sur le serveur de Data Workbench {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Une autre façon de vérifier l&#39;exécution de l&#39;émetteur consiste à configurer des alertes administratives automatisées dans le [!DNL data workbench server]. Lorsque des alertes d&#39;administration ont été configurées, [!DNL data workbench server] génère une alerte par courriel lorsqu&#39;il n&#39;a reçu aucune donnée d&#39;un [!DNL Sensor] configuré et précédemment connecté dans le délai spécifié dans le paramètre [!DNL Sensor] Délai d&#39;alerte (min) du fichier [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg]. Pour plus d&#39;informations sur la configuration des alertes administratives, consultez le *Guide d&#39;installation et d&#39;administration des produits serveur*.

## Vérification de l&#39;état du système du capteur {#section-de9d7e359242487a9fbead4ed65aebbc}

Une autre façon de vérifier que l&#39;émetteur est en cours d&#39;exécution consiste à vérifier manuellement le [!DNL Servers Manager] en Data Workbench.

**Pour vue à la variable[!DNL Servers Manager]**

* En Data Workbench, cliquez avec le bouton droit de la souris dans un espace de travail, cliquez sur **[!UICONTROL Admin]**, puis sous [!DNL Manage], cliquez sur **[!UICONTROL Servers]**.

Si l&#39;icône [!DNL Sensor] est verte, l&#39;émetteur est en cours d&#39;exécution.

Pour plus d&#39;informations sur [!DNL Servers Manager], consultez le chapitre Interfaces administratives du *Data Workbench [!DNL Sensor] Guide*.
