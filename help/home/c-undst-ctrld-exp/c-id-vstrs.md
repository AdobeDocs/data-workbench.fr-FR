---
description: Une configuration type de Site utilise des cookies pour identifier de manière unique les visiteurs de votre site Web et suivre leur comportement au fil du temps.
solution: Insight,Analytics
title: Comment Le Site Identifie-T-Il Les Visiteurs ?
topic: Data workbench
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Comment Le Site Identifie-T-Il Les Visiteurs ?{#how-does-site-identify-visitors}

Une configuration type de Site utilise des cookies pour identifier de manière unique les visiteurs de votre site Web et suivre leur comportement au fil du temps.

La première fois qu’un navigateur particulier (considéré comme un visiteur) émet une requête de votre site Web, [!DNL Sensor] il travaille avec votre serveur Web pour définir un cookie persistant (par défaut [!DNL cs(cookie)(v1st)]), interprété en interne dans le système comme [!DNL x-trackingid]. Ce cookie n’est défini qu’une seule fois, lors de la toute première requête envoyée à votre site Web par ce visiteur. Il est ensuite collecté auprès de ce visiteur chaque fois que ce navigateur émet une requête (page ou objet incorporé) de votre site Web à l’avenir.

L’acceptation d’un cookie persistant est laissée à la discrétion du navigateur. Si un utilisateur choisit de bloquer les cookies persistants, ses requêtes de pages vues sont toujours enregistrées, mais les données de mesure de ces requêtes ne sont pas corrélées à un visiteur particulier ou à ses sessions sur le site Web, sauf si vous implémentez une autre méthode d’identification des visiteurs, comme l’utilisation de la transformation de hachage sur les champs IP et UserAgent.

>[!NOTE]
>
>Les expériences de site ne peuvent être analysées que dans les jeux de données où la seule méthode d’identification des visiteurs utilisée est la méthode de cookie persistant [!DNL Sensor] définie. Les capteurs exécutés sur des serveurs J2EE (JBoss, Tomcat, WebLogic et WebSphere) ne prennent pas en charge l’expérimentation contrôlée.

Lors d’une expérience contrôlée, les utilisateurs qui n’acceptent pas les cookies peuvent être placés dans différents groupes d’expériences d’un clic à l’autre. Cela devient un problème uniquement si vous effectuez votre analyse de test avec le filtre de session rompue désactivé dans [!DNL Insight], ce qu’Adobe ne recommande pas.

Pour plus d’informations sur le filtre de session rompue, consultez le * [!DNL Insight] Guide de l’utilisateur*.

Si un visiteur efface le cookie au cours d’une expérience, un nouveau cookie lui est affecté et peut éventuellement être affecté à un autre groupe. Comme Adobe identifie le visiteur comme étant nouveau, l’expérience n’est pas invalidée.
