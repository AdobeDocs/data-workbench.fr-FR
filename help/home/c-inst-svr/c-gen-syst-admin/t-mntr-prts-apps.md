---
description: Pour surveiller plus attentivement votre mise en oeuvre, vous pouvez surveiller tous les ports de vos machines serveur ainsi que les logiciels s’exécutant sur chacun de ces ports.
title: Surveillance des ports et des applications
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
exl-id: 418b2e5c-42ec-40f0-9cae-375194288143
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 4%

---

# Surveillance des ports et des applications{#monitoring-ports-and-applications}

Pour surveiller plus attentivement votre mise en oeuvre, vous pouvez surveiller tous les ports de vos machines serveur ainsi que les logiciels s’exécutant sur chacun de ces ports.

**Fréquence recommandée :** Toutes les 5-10 minutes

À l’aide d’une application ou d’un script, vous pouvez surveiller le port TCP sur lequel s’exécute chaque application (généralement le port 80 ou 443) pour vous assurer que l’application est liée à ce port. Pour ce faire, vous demandez une page d’état de l’application à la machine que vous souhaitez surveiller.

**Pour demander la page d’état de l’application**

1. Sur l’ordinateur que vous souhaitez surveiller, modifiez les contrôles d’accès pour permettre à votre application de surveillance ou à votre script d’accéder à l’ordinateur. Pour obtenir des instructions, voir [Configuration du contrôle d’accès](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).
1. Connectez-vous à [!DNL https://IP Address/Status/], où l’adresse IP est l’adresse IP de la machine pour laquelle vous souhaitez recevoir le statut.

   Exemple : [!DNL https://127.0.0.1/Status/]

   La machine doit répondre avec une description de l’état du serveur. S’il ne répond pas, vérifiez vos journaux d’événements et contactez l’assistance clientèle d’Adobe.

   Pour plus d’informations sur ce type de surveillance avancée, veuillez contacter les services de conseil d’Adobe.
