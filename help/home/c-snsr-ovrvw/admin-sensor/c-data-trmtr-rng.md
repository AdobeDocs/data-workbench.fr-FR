---
description: Vérifiez si l'émetteur s'exécute en configurant des alertes, en vérifiant l'état du système du capteur, etc.
title: Confirmation que l’émetteur de données est en cours d’exécution
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---

# Confirmation que l’émetteur de données est en cours d’exécution{#confirming-that-the-data-transmitter-is-running}

Vérifiez si l&#39;émetteur s&#39;exécute en configurant des alertes, en vérifiant l&#39;état du système du capteur, etc.

**Fréquence recommandée :** Toutes les 5-10 minutes

* [Vérifiez que le processus de l&#39;émetteur est en cours d&#39;exécution.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Configurez les alertes administratives dans Insight Server.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Vérifiez l’état du système du capteur.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Vérification du processus d’émetteur {#section-79806fa3b7034a8eaf571a66e24874d7}

Une méthode pour vérifier que l&#39;émetteur est en cours d&#39;exécution consiste à vérifier que le processus de l&#39;émetteur [!DNL Sensor] est en cours d&#39;exécution sur chaque serveur web sur lequel une instance [!DNL Sensor] est installée. Le processus de l’émetteur apparaît sous la forme &quot;txlogd&quot; dans la liste des processus du serveur web. Vous pouvez effectuer cette vérification à l’aide d’un outil de surveillance du système.

## Configuration des alertes administratives sur le serveur du Data Workbench {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Une autre manière de vérifier que l’émetteur est en cours d’exécution consiste à configurer des alertes administratives automatisées dans la balise [!DNL data workbench server]. Une fois les alertes administratives configurées, la fonction [!DNL data workbench server] génère une alerte par email lorsqu’elle n’a reçu aucune donnée d’une instance [!DNL Sensor] configurée et précédemment connectée, dans la période spécifiée dans le paramètre [!DNL Sensor] Délai d’alerte (min) du fichier [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg]. Pour plus d’informations sur la configuration des alertes administratives, consultez le *Guide d’installation et d’administration des produits serveur*.

## Vérification de l’état du système du capteur {#section-de9d7e359242487a9fbead4ed65aebbc}

Une autre façon de vérifier que l&#39;émetteur est en cours d&#39;exécution consiste à vérifier manuellement la balise [!DNL Servers Manager] en Data Workbench.

**Pour afficher la variable[!DNL Servers Manager]**

* Dans Data Workbench, cliquez avec le bouton droit dans un espace de travail, cliquez sur **[!UICONTROL Admin]**, puis sous [!DNL Manage], cliquez sur **[!UICONTROL Servers]**.

Si l’icône d’un [!DNL Sensor] est verte, l’émetteur est en cours d’exécution.

Pour plus d’informations sur [!DNL Servers Manager], consultez le chapitre Interfaces administratives du *Data Workbench [!DNL Sensor] Guide*.
