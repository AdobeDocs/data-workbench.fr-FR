---
description: Une configuration type de Site utilise des cookies pour identifier de manière unique les visiteurs de votre site Web et suivre leur comportement au fil du temps.
solution: Analytics,Analytics
title: Comment le site identifie-t-il les visiteurs ?
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# Comment le site identifie-t-il les visiteurs ?{#how-does-site-identify-visitors}

Une configuration type de Site utilise des cookies pour identifier de manière unique les visiteurs de votre site Web et suivre leur comportement au fil du temps.

La première fois qu’un navigateur particulier (considéré comme un visiteur) émet une requête de votre site Web, [!DNL Sensor] travaille avec votre serveur Web pour définir un cookie persistant (par défaut [!DNL cs(cookie)(v1st)]), qui est interprété en interne dans le système comme [!DNL x-trackingid]. Ce cookie n’est défini qu’une seule fois, sur la toute première demande faite à votre site Web par ce visiteur. Il est ensuite collecté auprès de ce visiteur chaque fois que le navigateur effectue une requête (page ou objet incorporé) de votre site Web à l’avenir.

L’acceptation d’un cookie persistant est laissée à la discrétion du navigateur. Si un utilisateur choisit de bloquer les cookies persistants, ses requêtes de vue de page sont toujours consignées, mais les données de mesure de ces requêtes ne sont pas corrélées à un visiteur particulier ou à ses sessions sur le site Web, sauf si vous implémentez une autre méthode d’identification des visiteurs, telle que l’utilisation de la transformation Hash sur les champs IP et UserAgent.

>[!NOTE]
>
>Les expériences de site ne peuvent être analysées que dans des jeux de données où la seule méthode d&#39;identification des visiteurs utilisée est la méthode de cookie persistant [!DNL Sensor] définie. Les capteurs exécutés sur des serveurs J2EE (JBoss, Tomcat, WebLogic et WebSphere) ne prennent pas en charge les expérimentations contrôlées.

Au cours d’une expérience contrôlée, les utilisateurs qui n’acceptent pas les cookies peuvent être placés dans différents groupes d’expériences d’un clic à l’autre. Ceci devient un problème uniquement si vous effectuez votre analyse de test avec le filtre de session rompue désactivé dans [!DNL Insight], dont l’Adobe n’est pas recommandé.

Pour plus d&#39;informations sur le filtre de session rompue, consultez le * [!DNL Insight] Guide de l&#39;utilisateur*.

Si un visiteur efface le cookie au cours d’une expérience, un nouveau cookie est attribué au visiteur et peut éventuellement être affecté à un autre groupe. Comme l&#39;Adobe identifie le visiteur comme nouveau, l&#39;expérience n&#39;est pas invalidée.
