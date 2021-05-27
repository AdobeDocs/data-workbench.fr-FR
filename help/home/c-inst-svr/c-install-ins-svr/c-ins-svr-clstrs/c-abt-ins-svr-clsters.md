---
description: Une grappe de serveurs Insight est requise lorsque la quantité de données que vous souhaitez traiter et rendre accessible à vos utilisateurs d’Insight et de Report dépasse la capacité d’un seul serveur Insight.
title: À propos des clusters de serveurs Insight
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# À propos des clusters de serveurs Insight{#about-insight-server-clusters}

Une grappe de serveurs Insight est requise lorsque la quantité de données que vous souhaitez traiter et rendre accessible à vos utilisateurs d’Insight et de Report dépasse la capacité d’un seul serveur Insight.

En configurant une grappe [!DNL Insight Server], vous pouvez distribuer un seul jeu de données d’analyse sur plusieurs machines d’une grappe afin d’exploiter la puissance de traitement de plusieurs [!DNL Insight Servers].

La première étape de l’implémentation d’une grappe [!DNL Insight Server] consiste à allouer les machines [!DNL Insight Server] de votre grappe. La première [!DNL Insight Server] machine que vous configurez est votre [!DNL Insight Server] maître (parfois appelé votre [!DNL Insight Server] Principal).

>[!NOTE]
>
>Si vous utilisez une [!DNL Insight Server] unité de serveur de fichiers (FSU), Adobe vous recommande de configurer le FSU en tant que [!DNL Insight Server] maître. Pour plus d’informations sur la configuration d’un FSU, consultez le *Guide de configuration des jeux de données*.

Le [!DNL Insight Server] maître gère la communication entre les autres [!DNL Insight Servers] de la grappe (appelés serveurs de traitement ou, parfois, serveurs de requête) et les instances de [!DNL Insight] et [!DNL Report]. Pour un jeu de données donné, le traitement du fichier journal a lieu sur (un ou plusieurs) désigné [!DNL Insight Servers] (maître ou traitement) comme spécifié dans les fichiers de configuration [!DNL Insight Server]. Lorsque vous travaillez dans un environnement organisé en grappes, les installations [!DNL Insight] sont configurées pour accéder au [!DNL Insight Server] maître, mais les requêtes peuvent être gérées par l’un des [!DNL Insight Servers] de la grappe.

>[!NOTE]
>
>Le fichier **PAServer.cfg**. Si vous souhaitez envoyer des tâches de mise en grappe Predictive Analytics aux serveurs Insight, vous devez configurer le fichier [!DNL PAServer.cfg] pour gérer les envois de mise en grappe côté serveur. Le profil personnalisé doit hériter de [!DNL PAServer.cfg] du profil Analytics prédictif ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Définissez un *serveur de Principal* dans ce fichier et enregistrez le [!DNL PAServer.cfg] sur le site de mise en oeuvre.
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
>Les instructions de ce chapitre ne s&#39;appliquent pas à la création d&#39;une grappe [!DNL Insight Server] composée de plus de cinq (5) [!DNL Insight Servers]. Veuillez contacter Adobe pour obtenir les configurations système requises et les recommandations de configuration de profil pour les clusters de plus de cinq [!DNL Insight Servers].
