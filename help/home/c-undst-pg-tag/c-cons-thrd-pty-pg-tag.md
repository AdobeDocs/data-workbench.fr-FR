---
description: Informations conceptuelles sur le balisage tiers et la prévention du blocage des cookies à l’aide de P3P.
title: Considérations P3P pour le balisage de pages tiers
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
exl-id: 8eb521b6-802c-4d9f-a6b4-b1c4f694b8b8
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---

# Considérations P3P pour le balisage de pages tiers{#p-p-considerations-for-third-party-page-tagging}

Informations conceptuelles sur le balisage tiers et la prévention du blocage des cookies à l’aide de P3P.

## Présentation du balisage de pages tiers {#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

Dans la plupart des mises en oeuvre, le cookie persistant Adobe est considéré comme un cookie propriétaire. Les cookies propriétaires sont définis comme ceux associés au domaine hôte.

Supposons qu’un utilisateur visite https://www.example.com/. En supposant qu’un capteur soit installé et opérationnel sur le serveur web hébergeant le domaine, un cookie persistant Adobe est défini et considéré comme un cookie propriétaire. Vous pouvez toutefois collecter des données de mesure à partir d’un site tiers en utilisant des objets incorporés, qui sont demandés et chargés à partir de votre serveur qui exécute [!DNL Sensor] au lieu du serveur tiers hébergeant la page ou le programme publicitaire. Par exemple, https://www.example2.com/ diffuse une page web avec une requête d’objet incorporée diffusée à partir de https://www.example.com/. La requête pour l’objet incorporé à partir de https://www.example.com/ entraîne la définition d’un cookie. toutefois, dans ce contexte, le navigateur web ou l’agent-utilisateur voit le cookie comme un cookie tiers.

Dans les navigateurs Web plus récents tels que Microsoft IE6, les fonctionnalités de confidentialité filtrent les cookies en fonction de leurs stratégies compactes envoyées dans l’en-tête de réponse HTTP à partir du serveur Web. Dans les paramètres par défaut d’IE6, que la plupart des utilisateurs ne modifient jamais, les cookies tiers sont bloqués lorsqu’ils disposent de stratégies compactes inexistantes ou insatisfaisantes. La plupart des sites qui rencontrent des problèmes de blocage des cookies disposent de cookies tiers sur leur site qui ne disposent pas des stratégies compactes appropriées envoyées dans l’en-tête de réponse HTTP. En outre, certains problèmes de blocage des cookies se produisent lorsqu’un site est encadré par un autre site. Par exemple, une boutique en ligne faisant partie d’un portail d’achat en ligne peut apparaître dans un cadre fourni par le portail. Du point de vue du navigateur, le contenu du magasin peut apparaître comme du contenu tiers lorsqu’il est encadré par le portail. Cependant, si un visiteur se rend directement à la boutique en ligne sans passer par le portail, le contenu est un contenu propriétaire. Ainsi, la boutique en ligne trouve que ses cookies ne sont bloqués que lorsque les visiteurs arrivent par le biais du portail.

Les systèmes de messagerie Web posent un problème similaire. Si un visiteur d’un site web envoie une page web à un ami qui utilise un système de messagerie Web, le message électronique s’affiche sous la forme d’un contenu tiers dans le navigateur de l’ami, car il est encadré par le système de messagerie. Si des cookies sont associés à la page qui a été envoyée par courrier électronique, ils sont traités comme des cookies tiers par IE6.

## Utilisation de P3P pour empêcher le blocage des cookies {#section-96831cad887649f295aec6931750e41a}

P3P fournit une méthode standard permettant aux sites web de coder leurs politiques de confidentialité dans un format XML lisible par ordinateur. Les navigateurs web P3P et autres agents utilisateur P3P récupèrent automatiquement les stratégies de confidentialité P3P, les analysent et les comparent aux préférences de confidentialité d’un utilisateur.

Pour empêcher IE6 de bloquer les cookies sur votre site, vous devez vous assurer que :

1. Tous les cookies définis dans un contexte tiers sont associés à des stratégies de compression P3P.
1. La stratégie compacte appropriée est envoyée à l’aide d’un en-tête de réponse HTTP personnalisé.
1. IE6 considère que ces stratégies de compression sont satisfaisantes.
1. Si les cookies tiers sont définis par une autre entreprise, vous devrez peut-être leur demander d’activer P3P et de définir des stratégies de compression P3P. Tout hôte qui définit une stratégie compacte P3P doit également disposer d’une stratégie P3P complète correspondante. Les utilisateurs peuvent modifier leurs paramètres IE6 afin que les cookies soient bloqués sous d’autres conditions également. toutefois, le placement de stratégies compactes satisfaisantes sur des cookies tiers empêche la plupart des cookies IE6 de bloquer les cookies.

Voici un exemple d’un en-tête P3P de ce type :

```
P3P: policyref=” https://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

Dans cet exemple, le fichier [!DNL p3p.xml] est utilisé pour faire référence à un fichier [!DNL policy.xml] associé résidant sur votre serveur web qui indique le type d’informations collectées par votre site web, les méthodes de résolution des litiges auxquelles votre organisation adhère, la manière dont les données collectées sont utilisées, le propriétaire des données et d’autres informations standard relatives à la Confidentialité Internet. Les trois codes de caractères qui suivent le &quot;CP&quot; sont des codes de stratégie compacts qui émulent ce qui est indiqué dans votre fichier [!DNL policy.xml].

Tous les fichiers XML de stratégies et de stratégies doivent être adaptés à l’organisation pour laquelle ils sont déployés, en spécifiant précisément leurs politiques de confidentialité internes en ce qui concerne la collecte de données sur le site web. Vous trouverez en ligne une multitude d’éditeurs de stratégie P3P, ainsi que des informations plus détaillées sur la mise en oeuvre d’une politique de confidentialité appropriée sur votre site web.

Pour plus d’informations sur la façon dont Internet Explorer 6 gère les en-têtes P3P, consultez :

[https://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](https://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
