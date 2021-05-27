---
description: Une configuration type de Site utilise des cookies pour identifier de manière unique les visiteurs de votre site Web et suivre leur comportement au fil du temps.
solution: Analytics,Analytics
title: Comment le site identifie-t-il les visiteurs ?
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# Comment le site identifie-t-il les visiteurs ?{#how-does-site-identify-visitors}

Une configuration type de Site utilise des cookies pour identifier de manière unique les visiteurs de votre site Web et suivre leur comportement au fil du temps.

La première fois qu’un navigateur particulier (considéré comme un visiteur) émet une requête sur votre site web, [!DNL Sensor] travaille avec votre serveur web pour définir un cookie persistant (par défaut [!DNL cs(cookie)(v1st)]), qui est interprété en interne dans le système comme [!DNL x-trackingid]. Ce cookie n’est défini qu’une seule fois, à la toute première demande envoyée à votre site web par ce visiteur. Il est ensuite collecté auprès de ce visiteur chaque fois que ce navigateur émet une requête (page ou objet incorporé) de votre site web à l’avenir.

L’acceptation d’un cookie persistant est à la discrétion du navigateur. Si un utilisateur choisit de bloquer les cookies persistants, ses requêtes de pages vues sont toujours consignées, mais les données de mesure de ces requêtes ne sont pas corrélées à un visiteur particulier ou à ses sessions sur le site web, sauf si vous implémentez une autre méthode d’identification des visiteurs, telle que l’utilisation de la transformation de hachage sur les champs IP et UserAgent .

>[!NOTE]
>
>Les expériences de site ne peuvent être analysées que dans des jeux de données où la seule méthode d’identification des visiteurs utilisée est la [!DNL Sensor] méthode de cookie persistant définie. Les capteurs exécutés sur des serveurs J2EE (JBoss, Tomcat, WebLogic et WebSphere) ne prennent pas en charge l’expérimentation contrôlée.

Lors d’une expérience contrôlée, les utilisateurs qui n’acceptent pas les cookies peuvent être placés dans différents groupes d’expériences d’un clic à l’autre. Cela devient problématique uniquement si vous effectuez votre analyse de test avec le filtre de session endommagé désactivé dans [!DNL Insight], ce Adobe n’est pas recommandé.

Pour plus d’informations sur le filtre de session rompu, consultez le * [!DNL Insight] Guide de l’utilisateur*.

Si un visiteur efface le cookie au cours d’une expérience, il se voit attribuer un nouveau cookie et peut éventuellement être affecté à un autre groupe. Comme Adobe identifie le visiteur comme nouveau, l’expérience n’est pas invalidée.
