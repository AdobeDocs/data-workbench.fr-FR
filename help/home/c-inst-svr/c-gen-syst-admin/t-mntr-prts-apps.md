---
description: Pour contrôler plus précisément votre mise en oeuvre, vous pouvez surveiller tous les ports de vos machines serveur ainsi que les produits logiciels qui s'exécutent sur chacun de ces ports.
title: Surveillance des ports et des applications
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
exl-id: 418b2e5c-42ec-40f0-9cae-375194288143
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 4%

---

# Surveillance des ports et des applications{#monitoring-ports-and-applications}

Pour contrôler plus précisément votre mise en oeuvre, vous pouvez surveiller tous les ports de vos machines serveur ainsi que les produits logiciels qui s&#39;exécutent sur chacun de ces ports.

**Fréquence recommandée :** toutes les 5 à 10 minutes

A l’aide d’une application ou d’un script, vous pouvez surveiller le port TCP sur lequel s’exécute chaque application (généralement le port 80 ou 443) pour vous assurer que l’application est liée à ce port. Pour ce faire, vous demandez à l’ordinateur que vous souhaitez surveiller une page d’état d’application.

**Pour demander la page d’état de la demande de service financier**

1. Sur l’ordinateur que vous souhaitez surveiller, modifiez les Contrôles d&#39;accès pour permettre à votre application de surveillance ou à votre script d’accéder à l’ordinateur. Pour obtenir des instructions, voir [Configuration du Contrôle d&#39;accès](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).
1. Connectez-vous à [!DNL https://IP Address/Status/], où l’adresse IP est l’adresse IP de l’ordinateur pour lequel vous souhaitez recevoir le statut.

   Exemple : [!DNL https://127.0.0.1/Status/]

   L&#39;ordinateur doit répondre avec une description de l&#39;état du serveur. S’il ne répond pas, vérifiez vos journaux de événement et contactez le service à la clientèle Adobe.

   Pour plus d&#39;informations sur ce type de surveillance avancée, veuillez contacter les Services de conseil en Adobe.
