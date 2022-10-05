---
description: Site utilise des cookies pour identifier de manière unique les visiteurs de votre site web et suivre leur comportement au fil du temps.
title: Compréhension du cookie v1st
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
exl-id: c5e8e1cb-686b-4d31-821e-60beb2808f80
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 2%

---

# Compréhension du cookie v1st{#understanding-the-v-st-cookie}

{{eol}}

Site utilise des cookies pour identifier de manière unique les visiteurs de votre site web et suivre leur comportement au fil du temps.

la première fois qu’un navigateur particulier (considéré comme un visiteur) émet une requête sur votre site web, [!DNL Sensor] fonctionne avec votre serveur web pour définir un cookie persistant, cs(cookie)(v1st), qui est interprété en interne dans le système comme x-trackingid. Ce cookie persistant est défini en plus de tout autre cookie que votre site peut autrement définir. Ce cookie optimise votre capacité à effectuer le suivi de vos visiteurs au cours de plusieurs sessions, ce qui permet de réaliser de nombreux types d’analyses qui sont par ailleurs impossibles.

[!DNL Sensor] attribue une clé numérique 64 bits dans le cookie afin d’identifier les nouveaux visiteurs qui font une demande du site en tant qu’identifiant unique. Lorsque la variable [!DNL Sensor] voit une requête d’un navigateur, il vérifie si &quot;cs(cookie)(v1st)&quot;, un cookie persistant propriétaire défini par [!DNL Sensor], existe dans les données de requête. Si cs(cookie)(v1st) n’est pas présent, [!DNL Sensor], par le biais de votre serveur web, indique au navigateur de le définir. Contrairement aux autres solutions, [!DNL Sensor] peut définir ce cookie sur la première requête du visiteur.

Vous trouverez ci-dessous l’en-tête de cookie persistant standard envoyé au navigateur à sa première requête de votre site par votre serveur web, en direction de [!DNL Sensor]. Le format peut être défini au moment de la configuration si un nom ou une date d’expiration différents sont souhaités. Par exemple :

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

Ce cookie n’est défini qu’une seule fois, à la toute première requête envoyée à votre site par ce visiteur. Il est ensuite collecté auprès de ce visiteur chaque fois que ce navigateur émet une requête (page ou objet incorporé) de votre site à l’avenir. Le cookie est d’une taille très réduite afin de minimiser la quantité de bande passante utilisée pour le transmettre à vos serveurs, à chaque demande de ce navigateur vers votre site.

L’acceptation d’un cookie persistant est à la discrétion du navigateur. La plupart des utilisateurs du web comprennent ce que font les cookies et reconnaissent également que les cookies propriétaires leur offrent un avantage précieux en leur permettant de personnaliser le contenu du site selon leurs préférences. Ces cookies propriétaires ne sont pas bloqués par les paramètres de sécurité par défaut des navigateurs courants. Si un utilisateur choisit de bloquer les cookies propriétaires, ses requêtes de pages vues sont toujours consignées, mais les données de mesure de ces requêtes ne peuvent pas être corrélées de manière fiable à un visiteur particulier ou à ses sessions sur le site. De nombreux sites, en particulier les sites dynamiques sophistiqués, utilisent déjà des cookies propriétaires, qui sont souvent nécessaires pour permettre aux applications web de fonctionner pour le visiteur. Un pas en arrière par rapport à un cookie persistant est un cookie de session, qui permet à une série de requêtes d’être liées en une session, mais n’autorise pas le suivi des visiteurs intersessions. [!DNL Site] est capable de mettre en session les données des visiteurs en fonction des cookies de session ou du numéro IP, mais les deux méthodes détournent considérablement des types et de la valeur de l’analyse qui peuvent être effectués avec [!DNL Site] ou tout autre système d’analyse et de reporting d’activités web.
