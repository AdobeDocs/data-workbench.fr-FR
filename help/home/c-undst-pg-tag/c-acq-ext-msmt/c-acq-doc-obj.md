---
description: A l’aide du modèle d’objet de Document JavaScript, d’autres méthodes de script peuvent être utilisées pour augmenter la demande de fichier zig.js.
title: Acquisition d’objets de document
uuid: 7681c337-b147-4937-9d9c-0ff48d9bdd00
exl-id: eae6609c-be86-44cf-a1a1-69ffb43231fa
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# Acquisition d’objets de document{#acquiring-document-objects}

A l’aide du modèle d’objet de Document JavaScript, d’autres méthodes de script peuvent être utilisées pour augmenter la demande de fichier zig.js.

Des informations telles que la valeur des balises META, les valeurs d’ID des balises DIV, etc., peuvent être référencées par nom et collectées en tant que variables à utiliser en analyse. Par exemple, pour capturer dynamiquement les informations contenues dans l’élément META du document HTML, vous pouvez utiliser la syntaxe JavaScript suivante :

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var m0 = document.getElementsByTagName('META')[0]; //define the first instance of META 
var metacontent = m0.getAttribute('content'); //get the ‘content’ value of META 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_1"] = metacontent; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

| Données collectées | Description | Exemple |
|---|---|---|
| v_1= | Valeur associée à la variable de chaîne de requête METAVALUE. Cette valeur représente les données dans l’élément META du document HTML. | v_1=Cette page présente le contenu associé à la page de remerciement de la commande. |

Une fois les données collectées, vous pouvez configurer le serveur de l’outil de données pour traiter ces données de mesure à des fins d’analyse et de rapports.
