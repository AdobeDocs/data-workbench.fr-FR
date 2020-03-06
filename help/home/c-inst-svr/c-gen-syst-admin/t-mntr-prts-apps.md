---
description: Pour surveiller plus précisément votre implémentation, vous pouvez surveiller tous les ports sur les ordinateurs de votre serveur ainsi que les produits logiciels qui s'exécutent sur chacun de ces ports.
solution: Insight
title: Surveillance des ports et des applications
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Surveillance des ports et des applications{#monitoring-ports-and-applications}

Pour surveiller plus précisément votre implémentation, vous pouvez surveiller tous les ports sur les ordinateurs de votre serveur ainsi que les produits logiciels qui s&#39;exécutent sur chacun de ces ports.

**Fréquence recommandée :** Toutes les 5 à 10 minutes

A l’aide d’une application ou d’un script, vous pouvez surveiller le port TCP sur lequel s’exécute chaque application (généralement le port 80 ou 443) pour vous assurer que l’application est liée à ce port. Pour ce faire, vous demandez une page d’état d’application à l’ordinateur que vous souhaitez surveiller.

**Pour demander la page d’état de la demande de service financier**

1. Sur l’ordinateur que vous souhaitez surveiller, modifiez les contrôles d’accès pour permettre à votre application de surveillance ou à votre script d’accéder à l’ordinateur. Pour obtenir des instructions, voir [Configuration du contrôle](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)d’accès.
1. Connectez-vous à [!DNL https://IP Address/Status/], où Adresse IP est l’adresse IP de l’ordinateur pour lequel vous souhaitez recevoir le statut.

   Exemple : [!DNL https://127.0.0.1/Status/]

   L’ordinateur doit répondre avec une description de l’état du serveur. S’il ne répond pas, vérifiez vos journaux d’événements et contactez le service à la clientèle d’Adobe.

   Pour plus d’informations sur ce type de surveillance avancée, contactez les services de conseil Adobe.

