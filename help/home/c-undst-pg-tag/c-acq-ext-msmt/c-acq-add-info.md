---
description: Des variables de chaîne de requête peuvent être ajoutées à une requête JavaScript pour collecter des mesures supplémentaires lorsqu’une requête est effectuée.
title: Acquisition d’informations supplémentaires
uuid: 0a8075e9-4986-42c4-b505-3985b433cf8e
exl-id: ad4f5e08-b7b7-4de3-b0c2-71440facb2d1
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 4%

---

# Acquisition d’informations supplémentaires{#acquiring-additional-information}

Des variables de chaîne de requête peuvent être ajoutées à une requête JavaScript pour collecter des mesures supplémentaires lorsqu’une requête est effectuée.

Ces variables peuvent être ajoutées manuellement ou par script dans la page elle-même.

Des informations supplémentaires pouvant être acquises à partir d’une page peuvent être ajoutées à l’objet incorporé via un script à l’aide du code suivant comme exemple :

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE
var v = {};
v["_pn"] = "Application Form";
v["_1"] = “99.99”;
v["_2"] = "visa";
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>
<noscript>

<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>
<!-- END REFERENCE PAGE TAG-->
```

Dans cet exemple, les variables de script pour v_1 et v_2 peuvent être dérivées d’une autre fonction de votre page web. Les variables ont été insérées comme exemples. Outre les mesures de base acquises à chaque demande, les mesures étendues suivantes seraient acquises avec la demande de l’URL ci-dessus :

| Données collectées | Description | Exemple |
|---|---|---|
| v_pn= | Valeur associée à la variable de chaîne de requête v_pn | v_pn=Formulaire d’application |
| v_1= | Valeur associée à la variable de chaîne de requête v_1 | v_1=99.99 |
| v_2= | Valeur associée à la variable de chaîne de requête v_2 | v_2=visa |
