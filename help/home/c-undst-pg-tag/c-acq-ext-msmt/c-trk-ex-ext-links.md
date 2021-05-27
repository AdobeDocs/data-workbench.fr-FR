---
description: Capture de l’activité sur des liens de site web tiers pour activer l’analyse Cible de sortie.
title: Suivi des sorties vers des liens externes
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
exl-id: fd7434e9-cd66-408e-baa9-6a0df4039786
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 6%

---

# Suivi des sorties vers des liens externes{#tracking-exits-to-external-links}

Capture de l’activité sur des liens de site web tiers pour activer l’analyse Cible de sortie.

Les pages web peuvent contenir des liens vers des sites web tiers. L’activité entre ces liens peut être capturée afin d’activer l’analyse Cible de sortie, en particulier dans le cas où le site tiers est responsable du paiement des frais de référence lors de la réception de ces renvois. Comme l’événement click est écrit par défaut dans les fichiers journaux du système tiers, des modifications doivent être apportées au lien pour que l’événement click soit capturé localement. Le lien tiers présent dans votre site web doit être modifié comme suit :

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

En effectuant la requête pour le fichier [!DNL PageExit.htm] , la valeur v_eurl est collectée à des fins d’analyse. En outre, lorsque [!DNL PageExit.htm] est chargé, il redirige immédiatement vers l’emplacement cible v_eurl spécifié.

| Données collectées | Description | Exemple |
|---|---|---|
| v_eurl | Valeur associée à la variable de chaîne de requête v_eurl. Cette valeur représente l’URL cible du lien présent dans la page HTML. | v_eurl=www.othersite.com |
