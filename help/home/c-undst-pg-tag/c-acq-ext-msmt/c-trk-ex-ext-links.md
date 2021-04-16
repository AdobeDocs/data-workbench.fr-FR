---
description: Capture de l’activité sur les liens de sites Web tiers pour activer l’analyse de sortie de Cible.
title: Suivi des sorties vers des liens externes
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
exl-id: fd7434e9-cd66-408e-baa9-6a0df4039786
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 6%

---

# Suivi des sorties vers des liens externes{#tracking-exits-to-external-links}

Capture de l’activité sur les liens de sites Web tiers pour activer l’analyse de sortie de Cible.

Les pages Web peuvent contenir des liens vers des sites Web tiers, et l&#39;activité entre ces liens peut être capturée pour activer l&#39;analyse de Cible de sortie, en particulier dans le cas où le site tiers est responsable du paiement des frais de renvoi lorsque de tels renvois sont reçus. Le événement de clics étant écrit par défaut dans les fichiers journaux du système tiers, des modifications doivent être apportées au lien pour que le événement de clics soit capturé localement. Le lien tiers présent sur votre site Web doit être modifié comme suit :

```
<A HREF=”http://www.myserver.com/PageExit.htm?v_eurl=http://www.othersite.com”>
```

Le fichier [!DNL PageExit.htm] référencé doit être créé et structuré de manière à contenir le script suivant :

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

En faisant la demande du fichier [!DNL PageExit.htm], la valeur v_eurl est collectée à des fins d’analyse. De plus, lorsque [!DNL PageExit.htm] est chargé, il redirige immédiatement vers l&#39;emplacement de cible v_eurl spécifié.

| Données collectées | Description | Exemple |
|---|---|---|
| v_eurl | Valeur associée à la variable de chaîne de requête v_eurl. Cette valeur représente l’URL de cible du lien présent dans la page HTML. | v_eurl=www.othersite.com |
