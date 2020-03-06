---
description: Vérifiez si l’émetteur est en cours d’exécution en configurant des alertes, en vérifiant l’état du système du capteur, etc.
solution: Insight
title: Confirmation de l’exécution de l’émetteur de données
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Confirmation de l’exécution de l’émetteur de données{#confirming-that-the-data-transmitter-is-running}

Vérifiez si l’émetteur est en cours d’exécution en configurant des alertes, en vérifiant l’état du système du capteur, etc.

**Fréquence recommandée :** Toutes les 5 à 10 minutes

* [Vérifiez que le processus de l’émetteur est en cours d’exécution.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Configurez les alertes administratives dans Insight Server.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [Vérifiez l&#39;état du système du capteur.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Vérification du processus d&#39;émetteur {#section-79806fa3b7034a8eaf571a66e24874d7}

Une méthode pour vérifier que l’émetteur est en cours d’exécution consiste à vérifier que le processus de l’ [!DNL Sensor] émetteur est en cours d’exécution sur chaque serveur Web sur lequel une [!DNL Sensor] instance est installée. Le processus d’émetteur apparaît sous la forme &quot;txlogd&quot; dans la liste des processus du serveur Web. Vous pouvez effectuer cette vérification à l’aide d’un outil de surveillance du système.

## Configuration des alertes d’administration dans le serveur Outils de données {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Une autre manière de vérifier que l’émetteur est en cours d’exécution consiste à configurer des alertes administratives automatisées dans le [!DNL data workbench server]. Lorsque des alertes d’administration ont été configurées, la [!DNL data workbench server] fonction génère une alerte par courrier électronique lorsqu’elle n’a reçu aucune donnée d’une personne configurée et précédemment connectée [!DNL Sensor] dans la période spécifiée dans le paramètre [!DNL Sensor] Délai d’expiration d’alerte (min) du [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg] fichier. Pour plus d&#39;informations sur la configuration des alertes d&#39;administration, consultez le Guide *d&#39;installation et d&#39;administration des produits* serveur.

## Vérification de l&#39;état du système du capteur {#section-de9d7e359242487a9fbead4ed65aebbc}

Une autre manière de vérifier que l’émetteur est en cours d’exécution consiste à vérifier manuellement le [!DNL Servers Manager] contenu dans les Outils de données.

**Pour afficher le[!DNL Servers Manager]**

* Dans Outils de données, cliquez avec le bouton droit dans un espace de travail, cliquez sur **[!UICONTROL Admin]**, puis sous [!DNL Manage], cliquez sur **[!UICONTROL Servers]**.

Si l’icône d’un [!DNL Sensor] est verte, l’émetteur est en cours d’exécution.

Pour plus d’informations sur la [!DNL Servers Manager]solution, voir le chapitre Interfaces d’administration du Guide *des outils de[!DNL Sensor]données*.
