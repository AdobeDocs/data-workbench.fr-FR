---
description: Une grappe de serveurs Insight est requise lorsque la quantité de données que vous souhaitez traiter et rendre accessible à vos utilisateurs d’Insight et de Report dépasse la capacité d’un seul serveur Insight.
title: À propos des clusters de serveurs Insight
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# À propos des clusters de serveurs Insight{#about-insight-server-clusters}

Une grappe de serveurs Insight est requise lorsque la quantité de données que vous souhaitez traiter et rendre accessible à vos utilisateurs d’Insight et de Report dépasse la capacité d’un seul serveur Insight.

En configurant un cluster [!DNL Insight Server], vous pouvez distribuer un jeu de données d&#39;analyse unique sur plusieurs ordinateurs d&#39;un cluster afin d&#39;exploiter la puissance de traitement de plusieurs [!DNL Insight Servers].

La première étape de l&#39;implémentation d&#39;un cluster [!DNL Insight Server] consiste à allouer les machines [!DNL Insight Server] de votre cluster. La première machine [!DNL Insight Server] que vous configurez est votre maître [!DNL Insight Server] (parfois appelé votre Principal [!DNL Insight Server]).

>[!NOTE]
>
>Si vous utilisez une [!DNL Insight Server] unité de serveur de fichiers (FSU), l&#39;Adobe vous recommande de configurer l&#39;unité de sauvegarde en tant que [!DNL Insight Server] maître. Pour plus d&#39;informations sur la configuration d&#39;un FSU, consultez le *Guide de configuration des jeux de données*.

Le maître [!DNL Insight Server] gère la communication entre les autres [!DNL Insight Servers] du cluster (appelés serveurs de traitement ou, parfois, serveurs de requête) et les instances de [!DNL Insight] et [!DNL Report]. Pour un jeu de données donné, le traitement du fichier journal se produit sur le (un ou plusieurs) [!DNL Insight Servers] (maître ou traitement) désigné dans les fichiers de configuration [!DNL Insight Server]. Lorsque vous travaillez dans un environnement organisé en grappes, les installations [!DNL Insight] sont configurées pour accéder au maître [!DNL Insight Server], mais les requêtes peuvent être gérées par l&#39;un des [!DNL Insight Servers] du cluster.

>[!NOTE]
>
>Le fichier **PAServer.cfg**. Si vous souhaitez envoyer des tâches de mise en grappe Predictive Analytics aux serveurs Insight, vous devez configurer le fichier [!DNL PAServer.cfg] pour gérer les envois de mise en grappe côté serveur. Le profil personnalisé doit hériter de [!DNL PAServer.cfg] du profil Analyses prédictives ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Définissez un *Principal Server* dans ce fichier et enregistrez [!DNL PAServer.cfg] sur le site d&#39;implémentation.
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
>Les instructions du présent chapitre ne s&#39;appliquent pas à la création d&#39;un [!DNL Insight Server] cluster composé de plus de cinq (5) [!DNL Insight Servers]. Veuillez contacter l&#39;Adobe pour obtenir la configuration système requise et les recommandations de configuration du profil pour les clusters de plus de cinq [!DNL Insight Servers].
