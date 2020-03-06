---
description: Le site utilise des cookies pour identifier de manière unique les visiteurs de votre site Web et suivre leur comportement au fil du temps.
solution: Analytics
title: Présentation du cookie v1st
topic: Data workbench
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Présentation du cookie v1st{#understanding-the-v-st-cookie}

Le site utilise des cookies pour identifier de manière unique les visiteurs de votre site Web et suivre leur comportement au fil du temps.

La première fois qu’un navigateur particulier (considéré comme un visiteur) émet une requête de votre site Web, [!DNL Sensor] il travaille avec votre serveur Web pour définir un cookie persistant, cs(cookie)(v1st), interprété en interne dans le système comme x-trackingid. Ce cookie persistant est défini en plus de tout autre cookie que votre site pourrait autrement définir. Ce cookie optimise votre capacité à effectuer le suivi de vos visiteurs sur plusieurs sessions, ce qui permet d’effectuer de nombreux types d’analyse qui, autrement, sont impossibles.

[!DNL Sensor] affecte une clé numérique 64 bits dans le cookie afin d’identifier les nouveaux visiteurs qui font une demande du site en tant qu’identifiant unique. Lorsque le [!DNL Sensor] voit une requête d’un navigateur, il vérifie si &quot;cs(cookie)(v1st)&quot;, un cookie persistant propriétaire défini par [!DNL Sensor], existe dans les données de requête. Si le cookie cs(cookie)(v1st) n’est pas présent, [!DNL Sensor], par l’intermédiaire de votre serveur Web, indique au navigateur de le définir. Contrairement aux autres solutions, [!DNL Sensor] il est possible de définir ce cookie sur la première requête du visiteur.

Vous trouverez ci-dessous l’en-tête de cookie persistant standard envoyé au navigateur à sa première demande de votre site par votre serveur Web, en direction de [!DNL Sensor]. Le format peut être défini au moment de la configuration si un nom ou une date d’expiration différent est souhaité. Par exemple :

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

Ce cookie est défini une seule fois, lors de la toute première requête effectuée sur votre site par ce visiteur. Il est ensuite collecté auprès de ce visiteur chaque fois que ce navigateur effectue une requête (page ou objet incorporé) de votre site à l’avenir. Le cookie est de très petite taille afin de minimiser la quantité de bande passante utilisée pour le transmettre à vos serveurs avec chaque requête de ce navigateur vers votre site.

L’acceptation d’un cookie persistant est laissée à la discrétion du navigateur. La plupart des internautes comprennent ce que font les cookies et reconnaissent également que les cookies propriétaires leur apportent un avantage précieux en permettant de personnaliser le contenu du site selon leurs préférences. Ces cookies propriétaires ne sont pas bloqués par les paramètres de sécurité par défaut des navigateurs courants. Si un utilisateur choisit de bloquer les cookies propriétaires, ses requêtes de pages vues sont toujours enregistrées, mais les données de mesure de ces requêtes ne peuvent pas être corrélées de manière fiable à un visiteur particulier ou à ses sessions sur le site. De nombreux sites, en particulier les sites dynamiques sophistiqués, utilisent déjà des cookies propriétaires, qui sont souvent nécessaires pour permettre aux applications Web de fonctionner pour le visiteur. Un cookie de session constitue une étape en arrière par rapport à un cookie persistant, qui permet à une série de requêtes d’être liées ensemble dans une session, mais ne permet pas le suivi des visiteurs entre les sessions. [!DNL Site] est capable de segmenter les données des visiteurs en fonction des cookies de session ou du numéro d’adresse IP, mais les deux méthodes détournent considérablement les types et la valeur de l’analyse qui peuvent être effectués avec [!DNL Site] ou tout autre système d’analyse et de création de rapports d’activité Web.
