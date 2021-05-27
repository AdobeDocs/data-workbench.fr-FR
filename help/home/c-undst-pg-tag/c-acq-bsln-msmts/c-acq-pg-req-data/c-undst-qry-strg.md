---
description: La chaîne de requête (cs-uri-query) est souvent utilisée par les applications web et les développeurs de site pour transmettre des informations d’une page à l’autre en raison de la nature sans état du HTTP.
title: Compréhension de la chaîne de requête
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
exl-id: b5281e5f-3eb7-4d6a-a7b3-9958cb430621
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 2%

---

# Compréhension de la chaîne de requête{#understanding-the-query-string}

La chaîne de requête (cs-uri-query) est souvent utilisée par les applications web et les développeurs de site pour transmettre des informations d’une page à l’autre en raison de la nature sans état du HTTP.

Dans de nombreux cas, les informations peuvent être transmises dans la chaîne de requête lorsqu’elles sont acquises par [!DNL Sensor] sur le serveur web. Ces informations peuvent être utilisées par [!DNL Site] pour éclairer la véritable structure du site, le chemin des visiteurs à travers celui-ci, ainsi que d&#39;autres informations.

Dans certains sites web dynamiques, les paires nom=valeur (variables) de la chaîne de requête sont importantes pour déterminer la page réelle demandée par un visiteur. Dans ce cas, les URL peuvent être structurées de la manière suivante ou similaire :

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

Dans cet exemple, PAGENAME est en fait l’indicateur de la page qui sera diffusée au demandeur de cette URL. De nombreux outils et services d’analyse de journaux Web limitent la capacité d’un opérateur de site à définir ce qu’une page se trouve sur son site en fonction des variables de chaîne de requête qui apparaissent dans les chaînes de requête des URL du site. Le serveur Data Workbench et Data Workbench peuvent être configurés pour utiliser ces noms de requête afin de définir des pages uniques. C’est important, car de nombreux systèmes interprètent les URL suivantes comme une même page, mais [!DNL Site] ne le fait pas.

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

De même, les développeurs et les applications du site ajoutent souvent de nombreuses variables de chaîne de requête aux URL d’un site qui n’ont rien à voir avec l’identification de la page réelle qui est demandée. Vous trouverez ci-dessous des exemples :

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

Dans cet exemple, la variable de chaîne de requête CAMPAIGN= a été ajoutée à l’URL. Cette variable CAMPAIGN est utilisée pour indiquer quelle campagne marketing a poussé un visiteur à sélectionner cette URL. [!DNL Site] peut être configuré pour utiliser ces informations de CAMPAIGN, mais les séparer de la définition de la page qu&#39;un visiteur a consultée afin que, dans votre liste de pages à des fins de reporting et d&#39;analyse, vous puissiez simplement voir ce qui suit :

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```
