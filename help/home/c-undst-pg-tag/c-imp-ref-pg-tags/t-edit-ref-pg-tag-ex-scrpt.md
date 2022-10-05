---
description: La balise de page de référence est constituée d’un script d’exécution de balise de page qui réside sur un serveur web. Lorsqu’elle est appelée, elle génère la collecte de toutes les données côté client pour la page demandée par le visiteur du site.
title: Modifier le script d’exécution de balise de page de référence
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
exl-id: bc922b59-716e-4e92-84b5-59a52620df03
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 7%

---

# Modifier le script d’exécution de balise de page de référence{#editing-the-reference-page-tag-execution-script}

{{eol}}

La balise de page de référence est constituée d’un script d’exécution de balise de page qui réside sur un serveur web. Lorsqu’elle est appelée, elle génère la collecte de toutes les données côté client pour la page demandée par le visiteur du site.

Vous pouvez modifier la variable [!DNL Reference Page Tag Execution Script] collecter des informations supplémentaires qui peuvent être identifiées lors des réunions de collecte des exigences avec l’équipe des services de conseil d’Adobe. Le [!DNL Reference Page Tag Execution Script] est relativement petite pour éviter les ajouts importants de téléchargement à vos pages web.

Les éléments suivants [!DNL Reference Page Tag Execution Script] Le code vous est fourni dans un fichier nommé [!DNL zig.js]:

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

Pour faciliter la collecte de données au moyen de l’utilisation de la variable [!DNL Reference Page Tag], procédez comme suit :

1. Créez ou placez le fichier image de 1 pixel par 1 nommé [!DNL zag.gif] dans un répertoire présent sur votre serveur web.
1. Modifiez la variable cd pour référencer le domaine approprié de votre site web ou du domaine de services gérés d’Adobe à partir duquel la variable [!DNL zag.gif] est référencé. La référence au fichier est créée lors de l’exécution de la variable [!DNL zig.js] fonctions de fichier. Par exemple :

   ```
   //www.mysite.com
   ```

1. Modifiez la variable cu pour référencer le chemin approprié vers l’emplacement de la variable [!DNL zag.gif] fichier . Par exemple

   ```
   /scripts
   ```

1. Assurez-vous que les en-têtes de contrôle du cache appropriés sont définis pour la variable [!DNL zag.gif] et [!DNL zig.js] fichiers .
