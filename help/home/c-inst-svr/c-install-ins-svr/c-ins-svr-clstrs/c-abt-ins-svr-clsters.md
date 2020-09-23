---
description: Une grappe de serveurs Insight est requise lorsque la quantité de données que vous souhaitez traiter et rendre accessible à vos utilisateurs d’Insight et de Report dépasse la capacité d’un seul serveur Insight.
solution: Analytics
title: À propos des clusters de serveurs Insight
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---


# À propos des clusters de serveurs Insight{#about-insight-server-clusters}

Une grappe de serveurs Insight est requise lorsque la quantité de données que vous souhaitez traiter et rendre accessible à vos utilisateurs d’Insight et de Report dépasse la capacité d’un seul serveur Insight.

En configurant une [!DNL Insight Server] grappe, vous pouvez distribuer un jeu de données d&#39;analyse unique sur plusieurs machines d&#39;une grappe afin d&#39;exploiter la puissance de traitement de plusieurs [!DNL Insight Servers]machines.

La première étape de l’implémentation d’une [!DNL Insight Server] grappe consiste à allouer les [!DNL Insight Server] machines de la grappe. La première [!DNL Insight Server] machine que vous configurez est votre maître [!DNL Insight Server] (parfois appelé votre Principal [!DNL Insight Server]).

>[!NOTE]
>
>Si vous utilisez une unité de serveur de [!DNL Insight Server] fichiers (FSU), l’Adobe vous recommande de configurer la FSU en tant que maître [!DNL Insight Server]. Pour plus d&#39;informations sur la configuration d&#39;un FSU, consultez le Guide *de configuration des jeux de* données.

Le maître [!DNL Insight Server] gère la communication entre l’autre [!DNL Insight Servers] dans la grappe (appelée serveurs de traitement ou, parfois, serveurs de requête) et les instances de [!DNL Insight] et [!DNL Report]. Pour un jeu de données donné, le traitement du fichier journal se produit sur le (un ou plusieurs) fichier désigné [!DNL Insight Servers] (maître ou traitement) comme indiqué dans les fichiers [!DNL Insight Server] de configuration. Lorsque vous travaillez dans un environnement organisé en grappes, [!DNL Insight] les installations sont configurées pour accéder au maître [!DNL Insight Server], mais les requêtes peuvent être gérées par n’importe lequel des [!DNL Insight Servers] membres de la grappe.

>[!NOTE]
>
>Fichier **PAServer.cfg** . Si vous souhaitez envoyer des tâches de mise en grappe Predictive Analytics aux serveurs Insight, vous devez configurer le [!DNL PAServer.cfg] fichier pour gérer les envois de mise en grappe côté serveur. Le profil personnalisé doit hériter de la valeur [!DNL PAServer.cfg] du profil Analyses prédictives ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Définissez un serveur *de* Principal dans ce fichier et enregistrez-le [!DNL PAServer.cfg] sur le site de mise en oeuvre.
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
>Les instructions du présent chapitre ne s&#39;appliquent pas à la création d&#39;un [!DNL Insight Server] groupe composé de plus de cinq (5) [!DNL Insight Servers]. Veuillez contacter l&#39;Adobe pour obtenir la configuration système requise et les recommandations de configuration du profil pour les grappes supérieures à cinq [!DNL Insight Servers].
