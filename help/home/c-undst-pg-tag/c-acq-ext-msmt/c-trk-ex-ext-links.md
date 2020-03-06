---
description: Capture de l’activité sur des liens de site Web tiers afin d’activer l’analyse Cible de sortie.
solution: Analytics
title: Suivi des sorties vers des liens externes
topic: Data workbench
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Suivi des sorties vers des liens externes{#tracking-exits-to-external-links}

Capture de l’activité sur des liens de site Web tiers afin d’activer l’analyse Cible de sortie.

Les pages Web peuvent contenir des liens vers des sites Web tiers, et l’activité sur ces liens peut être capturée pour activer l’analyse Cible de sortie, en particulier dans le cas où le site tiers est responsable du paiement des frais de référence lors de la réception de ces renvois. L’événement click étant écrit dans les fichiers journaux du système tiers par défaut, des modifications doivent être apportées au lien pour que l’événement click soit capturé localement. Le lien tiers présent sur votre site Web doit être modifié comme suit :

```
<A HREF=”http://www.myserver.com/PageExit.htm?v_eurl=http://www.othersite.com”>
```

Le [!DNL PageExit.htm] fichier référencé doit être créé et structuré de manière à contenir le script suivant :

```
<html> 
<head> 
 
<script> 
function getExitURLQuery(variable) 
{ 
 
var query = window.location.search.substring(1); 
var vars = query.split("&"); 
for (var i=0; i<vars.length; i++) 
{ 
var pair = vars[i].split("="); 
if (pair[0] == variable) 
{ 
return pair[1]; 
} 
 }  
} 
</script> 
 
<script> 
location.replace(getExitURLQuery("v_eurl")); 
</script>  
 
</head> 
</html>
```

En faisant la demande du [!DNL PageExit.htm] fichier, la valeur v_eurl est collectée à des fins d’analyse. De plus, lorsqu’ [!DNL PageExit.htm] est chargé, il redirige immédiatement vers l’emplacement cible v_eurl spécifié.

| Données collectées | Description | Exemple |
|---|---|---|
| v_eurl | Valeur associée à la variable de chaîne de requête v_eurl. Cette valeur représente l’URL cible du lien présent dans la page HTML. | v_eurl=www.othersite.com |

