---
description: La balise de page de référence se compose d’un script d’exécution des balises de page qui réside sur un serveur Web et, lorsqu’elle est appelée, elle génère la collecte de toutes les données côté client pour la page demandée par le visiteur du site.
solution: Analytics
title: Modification du script d’exécution des balises de page de référence
topic: Data workbench
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modification du script d’exécution des balises de page de référence{#editing-the-reference-page-tag-execution-script}

La balise de page de référence se compose d’un script d’exécution des balises de page qui réside sur un serveur Web et, lorsqu’elle est appelée, elle génère la collecte de toutes les données côté client pour la page demandée par le visiteur du site.

Vous pouvez modifier la section [!DNL Reference Page Tag Execution Script] pour collecter des informations supplémentaires qui peuvent être identifiées lors de la collecte des besoins avec l’équipe des services de conseil Adobe. La taille [!DNL Reference Page Tag Execution Script] est relativement petite afin d’éviter des ajouts importants aux téléchargements de vos pages Web.

Le [!DNL Reference Page Tag Execution Script] code suivant vous est fourni dans un fichier nommé [!DNL zig.js]:

```
//REFERENCE PAGE TAG 
// CONSTANTS 
var ct = "<img src="; 
var cd = "[PATH_TO_WEB_SERVER]"; //this should contain the domain of 
                               //the web site that will host the 
                                //page tag 
 
var cu = "[PATH_TO_WEB_PAGE_TAG_CODE]/zag.gif?Log=1";  
                                 //this should contain the full path to 
                                 //the zag.gif file (excluding domain) 
                                 //and include the query string of log=1 
var ce = ">"; 
var c = {}; 
c["sw"] = screen.width; 
c["sh"] = screen.height; 
c["cd"] = screen.colorDepth; 
var co = ""; 
 
for ( cKey in c ) { 
co = co+"&"+cKey+"="+escape(c[cKey]); 
} 
document.write(ct,cd,cu,co,ce); 
 
var d = {}; 
d["dt"] = document.title; 
d["dr"] = document.referrer; 
d["cb"] = new Date().getTime(); 
var vo = ""; 
 
if (typeof v != "undefined") { 
for ( vKey in v ) { 
vo = vo+"&"+vKey+"="+escape(v[vKey]); 
} 
} 
for ( dKey in d ) { 
vo = vo+"&"+dKey+"="+escape(d[dKey]); 
} 
document.write(ct,cd,cu,vo,ce); 
//END REFERENCE PAGE TAG 
```

Pour faciliter la collecte de données par l’utilisation de la [!DNL Reference Page Tag], procédez comme suit :

1. Créez ou importez le fichier image 1 pixel par 1 pixel nommé [!DNL zag.gif] dans un répertoire présent sur votre serveur Web.
1. Modifiez la variable cd pour référencer le domaine approprié de votre site Web ou du domaine de services gérés Adobe à partir duquel le [!DNL zag.gif] fichier est référencé. La référence au fichier est créée par l&#39;exécution des fonctions de [!DNL zig.js] fichier. Par exemple :

   ```
   //www.mysite.com
   ```

1. Modifiez la variable cu pour référencer le chemin d’accès approprié à l’emplacement du [!DNL zag.gif] fichier. Par exemple

   ```
   /scripts
   ```

1. Assurez-vous que les en-têtes de contrôle du cache appropriés sont définis pour les [!DNL zag.gif] fichiers et [!DNL zig.js] les fichiers.
