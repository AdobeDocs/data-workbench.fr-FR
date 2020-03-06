---
description: Une grappe de serveurs Insight est requise lorsque la quantité de données que vous souhaitez traiter et rendre accessible à vos utilisateurs d’Insight et de Report dépasse la capacité d’un seul serveur Insight.
solution: Insight
title: A propos des grappes de serveurs Insight
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# A propos des grappes de serveurs Insight{#about-insight-server-clusters}

Une grappe de serveurs Insight est requise lorsque la quantité de données que vous souhaitez traiter et rendre accessible à vos utilisateurs d’Insight et de Report dépasse la capacité d’un seul serveur Insight.

En configurant une [!DNL Insight Server] grappe, vous pouvez distribuer un jeu de données d’analyse unique sur plusieurs ordinateurs d’une grappe afin d’exploiter la puissance de traitement de plusieurs [!DNL Insight Servers]ordinateurs.

La première étape de l’implémentation d’une [!DNL Insight Server] grappe consiste à allouer les [!DNL Insight Server] ordinateurs de votre grappe. La première [!DNL Insight Server] machine que vous avez configurée est votre maître [!DNL Insight Server] (parfois appelé votre principal [!DNL Insight Server]).

>[!NOTE]
>
>Si vous utilisez une unité de serveur de [!DNL Insight Server] fichiers (FSU), Adobe vous conseille de configurer l’unité en tant que maître [!DNL Insight Server]. Pour plus d’informations sur la configuration d’un FSU, consultez le Guide *de configuration des jeux de* données.

Le maître [!DNL Insight Server] gère la communication entre les autres [!DNL Insight Servers] dans la grappe (appelés serveurs de traitement ou, parfois, serveurs de requête) et les instances de [!DNL Insight] et [!DNL Report]. Pour un jeu de données donné, le traitement du fichier journal se produit sur le (un ou plusieurs) fichier(s) désigné(s) [!DNL Insight Servers] (maître ou traitement) comme indiqué dans les fichiers [!DNL Insight Server] de configuration. Lorsque vous travaillez dans un environnement organisé en grappes, [!DNL Insight] les installations sont configurées pour accéder au maître [!DNL Insight Server], mais les requêtes peuvent être gérées par n’importe quel [!DNL Insight Servers] membre de la grappe.

>[!NOTE]
>
>Fichier **PAServer.cfg** . Si vous souhaitez envoyer des tâches de mise en grappe Predictive Analytics aux serveurs Insight, vous devez configurer le [!DNL PAServer.cfg] fichier pour gérer les envois de mise en grappe côté serveur. Le profil personnalisé doit hériter du profil Analyses prédictives ( [!DNL PAServer.cfg] [!DNL Server\Profiles\Predictive Analytics\Dataset]). Définissez un serveur *maître* dans ce fichier et enregistrez le serveur [!DNL PAServer.cfg] sur le site d’implémentation. >
>
```>
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```>



>[!IMPORTANT]
>
>Les instructions du présent chapitre ne s&#39;appliquent pas à la création d&#39;un [!DNL Insight Server] groupe composé de plus de cinq (5) [!DNL Insight Servers]. Contactez Adobe pour obtenir la configuration système requise et des recommandations de configuration de profil pour les grappes de plus de cinq [!DNL Insight Servers].

