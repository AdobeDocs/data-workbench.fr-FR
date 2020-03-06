---
description: La chaîne de requête (cs-uri-query) est souvent utilisée par les applications Web et les développeurs de sites pour transmettre des informations d'une page à l'autre en raison de la nature sans état du protocole HTTP.
solution: Analytics
title: Présentation de la chaîne de requête
topic: Data workbench
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Présentation de la chaîne de requête{#understanding-the-query-string}

La chaîne de requête (cs-uri-query) est souvent utilisée par les applications Web et les développeurs de sites pour transmettre des informations d&#39;une page à l&#39;autre en raison de la nature sans état du protocole HTTP.

Dans de nombreux cas, les informations peuvent être transmises dans la chaîne de requête lorsqu’elles sont acquises par [!DNL Sensor] le serveur Web. Ces informations peuvent être utilisées pour [!DNL Site] éclairer la structure réelle du site, le chemin des visiteurs à travers celui-ci, ainsi que d&#39;autres informations.

Dans certains sites Web dynamiques, les paires nom=valeur (variables) dans la chaîne de requête sont importantes pour déterminer la page réelle demandée par un visiteur. Dans ce cas, les URL peuvent être structurées de la manière suivante ou similaire :

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

Dans cet exemple, PAGENAME est en fait l&#39;indicateur de la page qui sera diffusée au demandeur de cette URL. De nombreux outils et services d’analyse des journaux Web limitent la capacité d’un opérateur de site à définir ce qu’est une page dans son site en fonction des variables de chaîne de requête qui se trouvent dans les chaînes de requête des URL du site. Le serveur de l’outil de données et l’outil de données peuvent être configurés pour utiliser ces noms de requête afin de définir des pages uniques. C’est important, car de nombreux systèmes interprètent les URL suivantes comme une même page, mais [!DNL Site] pas.

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

De même, les développeurs et les applications du site ajoutent souvent de nombreuses variables de chaîne de requête aux URL d’un site qui n’ont rien à voir avec l’identification de la page réelle demandée. Voici quelques exemples :

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

Dans cet exemple, la variable de chaîne de requête CAMPAIGN= a été ajoutée à l’URL. Cette variable CAMPAGNE est utilisée pour indiquer quelle campagne marketing a poussé un visiteur à sélectionner cette URL. [!DNL Site] peut être configuré pour utiliser ces informations de CAMPAGNE, tout en les séparant de la définition de la page qu’un visiteur a consultée afin que, dans votre liste de pages à des fins de création de rapports et d’analyse, vous puissiez simplement voir ce qui suit :

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

