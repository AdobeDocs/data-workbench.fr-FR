---
description: Informations conceptuelles sur le balisage tiers et la prévention du blocage des cookies à l’aide de P3P.
solution: Analytics
title: Points à prendre en compte pour le balisage de page tiers
topic: Data workbench
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Points à prendre en compte pour le balisage de page tiers{#p-p-considerations-for-third-party-page-tagging}

Informations conceptuelles sur le balisage tiers et la prévention du blocage des cookies à l’aide de P3P.

## Présentation du balisage de page tiers {#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

Dans la plupart des implémentations, le cookie persistant Adobe est affiché comme un cookie propriétaire. Les cookies propriétaires sont définis comme étant ceux associés au domaine hôte.

Supposons qu’un utilisateur visite http://www.example.com/. En supposant qu’un capteur soit installé et opérationnel sur le serveur Web hébergeant le domaine, un cookie persistant Adobe est défini et affiché comme cookie propriétaire. Vous pouvez toutefois collecter des données de mesure à partir d’un site tiers en utilisant des objets incorporés, qui sont demandés et chargés à partir de votre serveur en cours d’exécution [!DNL Sensor] au lieu du serveur tiers hébergeant la page ou le programme publicitaire. Par exemple, http://www.example2.com/ diffuse une page Web avec une requête d’objet incorporée diffusée à partir de http://www.example.com/. La demande d’objet incorporé à partir de http://www.example.com/ entraîne la définition d’un cookie ; toutefois, dans ce contexte, le navigateur Web ou l’agent utilisateur voit le cookie comme un cookie tiers.

Dans les nouveaux navigateurs Web, tels que Microsoft IE6, les fonctions de confidentialité filtrent les cookies en fonction de leurs stratégies compactes envoyées dans l’en-tête de réponse HTTP à partir du serveur Web. Dans les paramètres IE6 par défaut, que la plupart des utilisateurs ne modifient jamais, les cookies tiers sont bloqués lorsqu’ils ont des stratégies compactes inexistantes ou insatisfaisantes. La plupart des sites qui rencontrent des problèmes de blocage des cookies ont des cookies tiers sur leur site qui ne disposent pas des stratégies compactes appropriées envoyées dans l’en-tête de réponse HTTP. De plus, certains problèmes de blocage des cookies surviennent lorsqu’un site est encadré par un autre site. Par exemple, une boutique en ligne faisant partie d’un portail d’achat en ligne peut apparaître dans un cadre fourni par le portail. Du point de vue du navigateur, le contenu du magasin peut sembler être du contenu tiers lorsqu’il est créé par le portail. Toutefois, si un visiteur se rend directement à la boutique en ligne sans passer par le portail, le contenu sera du contenu propriétaire. Ainsi, la boutique en ligne trouve que ses cookies ne sont bloqués que lorsque les visiteurs arrivent par le biais du portail.

Les systèmes de messagerie Web posent le même problème. Si un visiteur de site Web envoie par courrier électronique une page Web à un ami qui utilise un système de messagerie Web, le message électronique s’affiche sous forme de contenu tiers dans le navigateur de l’ami, car il est encadré par le système de messagerie électronique. S’il existe des cookies associés à la page qui ont été envoyés par courrier électronique, ils sont traités comme des cookies tiers par IE6.

## Utilisation de P3P pour empêcher le blocage des cookies {#section-96831cad887649f295aec6931750e41a}

P3P fournit une méthode standard pour que les sites Web encodent leurs règles de confidentialité dans un format XML lisible par ordinateur. Les navigateurs Web compatibles P3P et d’autres agents utilisateur P3P récupèrent automatiquement les stratégies de confidentialité P3P, les analysent et les comparent aux préférences de confidentialité d’un utilisateur.

Pour empêcher IE6 de bloquer les cookies sur votre site, vous devez vous assurer que :

1. Tous les cookies définis dans un contexte tiers sont associés à des stratégies compactes P3P.
1. La stratégie compacte appropriée est envoyée à l’aide d’un en-tête de réponse HTTP personnalisé.
1. IE6 considère que ces politiques sont satisfaisantes.
1. Si les cookies tiers sont définis par une autre société, vous devrez peut-être leur demander d’activer P3P et de définir des stratégies compactes P3P. Tout hôte qui définit une stratégie compacte P3P doit également avoir une stratégie P3P complète correspondante. Les utilisateurs peuvent modifier leurs paramètres IE6 afin que les cookies soient bloqués dans d’autres conditions également ; toutefois, le fait de placer des stratégies compactes satisfaisantes sur des cookies tiers empêche la plupart des cookies IE6 de bloquer les cookies.

Voici un exemple d’en-tête P3P :

```
P3P: policyref=” http://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

Dans cet exemple, le fichier [!DNL p3p.xml] est utilisé pour référencer un [!DNL policy.xml] fichier associé résidant sur votre serveur Web qui indique le type d’informations collectées par votre site Web, les méthodes de résolution des litiges auxquelles votre organisation adhère, la manière dont les données collectées sont utilisées, le propriétaire des données et d’autres informations standard relatives à la confidentialité sur Internet. Les codes à trois caractères qui suivent le &quot;CP&quot; sont les codes de stratégie compacts qui imitent ce qui est indiqué dans votre [!DNL policy.xml] fichier.

Tous les fichiers XML de stratégies et de stratégies compactes doivent être adaptés à l’organisation pour laquelle ils sont déployés, en spécifiant avec précision leurs politiques de confidentialité internes en ce qui concerne la collecte de données sur le site Web. Une multitude d’éditeurs de politiques P3P peuvent être trouvés en ligne, ainsi que des informations plus détaillées sur la mise en oeuvre d’une politique de confidentialité appropriée dans votre site Web.

Pour plus d&#39;informations sur la façon dont Internet Explorer 6 gère les en-têtes P3P, veuillez visiter :

[http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
