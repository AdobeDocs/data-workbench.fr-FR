---
description: Une grappe de serveurs Insight est requise lorsque la quantité de données que vous souhaitez traiter et rendre accessible à vos utilisateurs d’Insight et de Report dépasse la capacité d’un seul serveur Insight.
title: À propos des clusters de serveurs Insight
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# À propos des clusters de serveurs Insight{#about-insight-server-clusters}

{{eol}}

Une grappe de serveurs Insight est requise lorsque la quantité de données que vous souhaitez traiter et rendre accessible à vos utilisateurs d’Insight et de Report dépasse la capacité d’un seul serveur Insight.

En configurant une [!DNL Insight Server] grappe, vous pouvez distribuer un seul jeu de données d’analyse sur plusieurs machines d’une grappe afin d’exploiter la puissance de traitement de plusieurs [!DNL Insight Servers].

La première étape de la mise en oeuvre d’un [!DNL Insight Server] La grappe doit allouer la variable [!DNL Insight Server] machines de votre grappe. Le premier [!DNL Insight Server] la machine que vous configurez est votre maître. [!DNL Insight Server] (parfois appelé votre Principal [!DNL Insight Server]).

>[!NOTE]
>
>Si vous utilisez une [!DNL Insight Server] File Server Unit (FSU), Adobe vous recommande de configurer le FSU en tant que maître. [!DNL Insight Server]. Pour plus d’informations sur la configuration d’un FSU, voir la section *Guide de configuration des jeux de données*.

Le maître [!DNL Insight Server] gère la communication entre les autres [!DNL Insight Servers] dans la grappe (appelée serveurs de traitement ou, parfois, serveurs de requête) et les instances de [!DNL Insight] et [!DNL Report]. Pour un jeu de données donné, le traitement du fichier journal a lieu sur (un ou plusieurs) désigné(e) [!DNL Insight Servers] (maître ou traitement) comme indiqué dans la variable [!DNL Insight Server] fichiers de configuration. Lorsque vous travaillez dans un environnement organisé en grappes, [!DNL Insight] Les installations sont configurées pour accéder au maître [!DNL Insight Server], mais les requêtes peuvent être gérées par l’un des [!DNL Insight Servers] dans la grappe.

>[!NOTE]
>
>Le **PAServer.cfg** fichier . Si vous souhaitez envoyer des tâches de mise en grappe Predictive Analytics aux serveurs Insight, vous devez configurer la variable [!DNL PAServer.cfg] pour gérer les envois de mise en grappe côté serveur. Le profil personnalisé doit hériter de la variable [!DNL PAServer.cfg] à partir du profil Analyses prédictives ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Définir une *Principal Server* dans ce fichier et enregistrez la variable [!DNL PAServer.cfg] sur le site de mise en oeuvre.
>
>
```
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```

>[!IMPORTANT]
>
>Les instructions de ce chapitre ne s&#39;appliquent pas à la création d&#39;un [!DNL Insight Server] grappe composée de plus de cinq (5) [!DNL Insight Servers]. Veuillez contacter Adobe pour obtenir les configurations système requises et les recommandations de configuration de profil pour les grappes de plus de cinq ans. [!DNL Insight Servers].
