---
description: La chaîne de requête (cs-uri-requête) est souvent utilisée par les applications Web et les développeurs de sites pour transmettre des informations de page en page en raison de la nature sans état du protocole HTTP.
title: Compréhension de la chaîne de requête
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
exl-id: b5281e5f-3eb7-4d6a-a7b3-9958cb430621
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 2%

---

# Compréhension de la chaîne de requête{#understanding-the-query-string}

La chaîne de requête (cs-uri-requête) est souvent utilisée par les applications Web et les développeurs de sites pour transmettre des informations de page en page en raison de la nature sans état du protocole HTTP.

Dans de nombreux cas, les informations peuvent être transmises dans la chaîne de requête lorsqu’elles sont acquises par [!DNL Sensor] sur le serveur Web. Ces informations peuvent être utilisées par [!DNL Site] pour éclairer la structure réelle du site, ainsi que le chemin des visiteurs à travers celui-ci, ainsi que d&#39;autres informations.

Dans certains sites Web dynamiques, les paires nom=valeur (variables) dans la chaîne de requête sont importantes pour déterminer la page réelle demandée par un visiteur. Dans ce cas, les URL peuvent être structurées de la manière suivante ou similaire :

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

Dans cet exemple, PAGENAME est en fait l&#39;indicateur de la page qui sera diffusée au demandeur de cette URL. De nombreux outils et services d&#39;analyse de journaux Web limitent la capacité d&#39;un opérateur de site à définir ce qu&#39;est une page de son site en fonction des variables de chaîne de requête qui se produisent dans les chaînes de requête des URL du site. Le serveur de l’outil de données et l’outil de données peuvent être configurés pour utiliser ces noms de requête afin de définir des pages uniques. Ceci est important car de nombreux systèmes interprètent les URL suivantes comme une même page, mais [!DNL Site] ne le fait pas.

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

De même, les développeurs et les applications du site ajoutent souvent de nombreuses variables de chaîne de requête dans les URL d&#39;un site qui n&#39;ont rien à voir avec l&#39;identification de la page réelle demandée. Les exemples sont illustrés ci-dessous :

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

Dans cet exemple, la variable de chaîne de requête CAMPAIGN= a été ajoutée à l’URL. Cette variable CAMPAIGN est utilisée pour indiquer quelle campagne marketing a poussé un visiteur à sélectionner cette URL. [!DNL Site] peuvent être configurés pour utiliser ces informations CAMPAIGN, mais séparez-les de la définition de la page qu&#39;un visiteur a consultée afin que, dans votre liste de pages à des fins de rapports et d&#39;analyse, vous puissiez simplement voir ce qui suit :

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```
