---
description: Le site utilise des cookies pour identifier de manière unique les visiteurs de votre site Web et suivre leur comportement au fil du temps.
title: Compréhension du cookie v1st
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
exl-id: c5e8e1cb-686b-4d31-821e-60beb2808f80
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 2%

---

# Compréhension du cookie v1st{#understanding-the-v-st-cookie}

Le site utilise des cookies pour identifier de manière unique les visiteurs de votre site Web et suivre leur comportement au fil du temps.

La première fois qu&#39;un navigateur particulier (considéré comme un visiteur) fait une demande de votre site Web, [!DNL Sensor] travaille avec votre serveur Web pour définir un cookie persistant, cs(cookie)(v1st), qui est interprété en interne dans le système comme x-trackingid. Ce cookie persistant est défini en plus de tout autre cookie que votre site pourrait autrement définir. Ce cookie optimise votre capacité à effectuer le suivi de vos visiteurs sur plusieurs sessions, ce qui permet d’effectuer de nombreux types d’analyses qui autrement seraient impossibles.

[!DNL Sensor] affecte une clé numérique 64 bits au cookie afin d’identifier les nouveaux visiteurs qui envoient une demande du site en tant qu’identifiant unique. Lorsque [!DNL Sensor] voit une requête d&#39;un navigateur, il vérifie si &quot;cs(cookie)(v1st)&quot;, un cookie persistant propriétaire défini par [!DNL Sensor], existe dans les données de la requête. Si cs(cookie)(v1st) n’est pas présent, [!DNL Sensor], par l’intermédiaire de votre serveur Web, indique au navigateur de le définir. Contrairement aux autres solutions, [!DNL Sensor] peut définir ce cookie sur la première demande du visiteur.

Vous trouverez ci-dessous l’en-tête de cookie persistant standard envoyé au navigateur à sa première demande de votre site par votre serveur Web, en direction de [!DNL Sensor]. Le format peut être défini au moment de la configuration si un nom ou une date d’expiration différent sont souhaités. Par exemple :

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

Ce cookie n&#39;est défini qu&#39;une seule fois, sur la toute première requête envoyée à votre site par ce visiteur. Il est ensuite collecté auprès de ce visiteur chaque fois que ce navigateur effectue une requête (page ou objet incorporé) de votre site dans le futur. Le cookie est de très petite taille afin de minimiser la quantité de bande passante utilisée pour le transmettre à vos serveurs avec chaque requête de ce navigateur vers votre site.

L’acceptation d’un cookie persistant est laissée à la discrétion du navigateur. La plupart des internautes comprennent ce que font les cookies et reconnaissent également que les cookies propriétaires leur apportent un avantage précieux en permettant de personnaliser le contenu du site selon leurs préférences. Ces cookies propriétaires ne sont pas bloqués par les paramètres de sécurité par défaut des navigateurs les plus utilisés. Si un utilisateur choisit de bloquer les cookies propriétaires, ses requêtes de vue de page sont toujours consignées, mais les données de mesure de ces requêtes ne peuvent pas être corrélées de manière fiable à un visiteur particulier ou à ses sessions sur le site. De nombreux sites, en particulier les sites dynamiques sophistiqués, utilisent déjà des cookies propriétaires, qui sont souvent nécessaires pour permettre aux applications Web de fonctionner pour le visiteur. Un cookie de session permet de lier une série de requêtes en une session, mais n’autorise pas le suivi entre visiteurs de session. [!DNL Site] est capable de segmenter les données des visiteurs en fonction des cookies de session ou par numéro d&#39;adresse IP, mais les deux méthodes détournent considérablement les types et la valeur de l&#39;analyse qui peut être réalisée avec  [!DNL Site] ou tout autre système d&#39;analyse et de rapports d&#39;activité Web.
