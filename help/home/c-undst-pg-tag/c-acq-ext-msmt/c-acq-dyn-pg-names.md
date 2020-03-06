---
description: Pour certains sites, il est nécessaire d’utiliser des requêtes d’objet incorporées pour transmettre des informations au serveur Web afin que les détails sur la page réellement diffusée puissent être acquis par Sensor et utilisés pour la création de rapports et l’analyse.
solution: Analytics
title: Acquisition de noms de page dynamiques
topic: Data workbench
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Acquisition de noms de page dynamiques{#acquiring-dynamic-page-names}

Pour certains sites, il est nécessaire d’utiliser des requêtes d’objet incorporées pour transmettre des informations au serveur Web afin que les détails sur la page réellement diffusée puissent être acquis par Sensor et utilisés pour la création de rapports et l’analyse.

Cela peut s’avérer nécessaire si l’URL de la page, telle qu’elle est vue par le serveur Web, n’indique pas le contenu de la page présenté au navigateur. Ce cas de figure résulte souvent de l’utilisation de systèmes de personnalisation ou de gestion dynamique du contenu dans lesquels le contenu réel diffusé dans une page est déterminé à la volée par l’URL, le cookie, les données associées et la logique applicative.

L&#39;implémentation d&#39;un objet incorporé pour collecter des mesures supplémentaires doit avoir un impact minimal sur les performances globales de votre site. Adobe suggère d’incorporer un fichier JavaScript comme objet utilisé pour collecter les attributs étendus. (Notez qu’un fichier JavaScript peut être incorporé sans impact potentiel sur la disposition et la présentation de votre page Web, comme cela peut se produire avec l’utilisation d’une image incorporée.) Pour capturer avec précision les informations transmises dans l’objet incorporé, Adobe suggère également d’utiliser un nom commun. À des fins d’attribution de noms, Adobe désigne cet objet comme [!DNL zig.js]. Le [!DNL zig.js] fichier doit être créé dans le répertoire approprié sur un serveur Web sur lequel [!DNL Sensor] est installé. Ce fichier doit exister pour que la requête ne renvoie pas de code d’erreur 404. Le contenu du fichier lui-même n’est pas important. Utilisez un fichier vide nommé [!DNL zig.js] pour minimiser le volume de trafic réseau généré par la demande.

Pour [!DNL Sensor] collecter un nom utilisable pour la page réellement diffusée, vous devez ajouter quelques lignes de code JavaScript aux pages dynamiques dont vous souhaitez effectuer le suivi ou auxquelles vous souhaitez ajouter un nom de page unique. Ce code incorpore un fragment de code JavaScript dans la page, ce qui entraîne l’envoi d’une demande d’objet incorporé tertiaire au serveur Web au moment du chargement de la page. Cette requête envoie des détails sur la page spécifique qui a été renvoyée au serveur Web. Le nom de la page réellement diffusée est renvoyé au serveur Web sous la forme d’une variable dans la chaîne de requête de la requête d’objet incorporé (dans ce cas, JavaScript).

En général, la requête d’objet incorporée dans chaque page HTML de ce type doit ressembler à ce qui suit :

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

[!DNL Log=1] veille à ce que [!DNL Sensor] la requête soit consignée dans le journal, en dépit des règles de filtrage de type de [!DNL Sensor] contenu, comme le filtrage des requêtes JavaScript et des demandes d’image avant leur stockage. La variable v_pn déclarée identifie le nom du contenu réel de la page diffusée, de sorte que [!DNL Site] connaisse le nom de la page réellement consultée par le visiteur. La valeur v_pn peut être établie manuellement ou par un autre script ou code d’application.

Une fois la valeur collectée, vous pouvez configurer le serveur de l’outil de données pour qu’il utilise le contenu de la variable de chaîne de requête (paire nom=valeur, par exemple, v_pn=Formulaire d’application) annexé à l’ [!DNL zag.gif] URI (par exemple, [!DNL http://www.mysite.com/pageserved.asp?v_pn=Application%20Form]), comme une augmentation de l’ [!DNL zag.gif] URI. En plus des mesures de base acquises avec chaque requête HTTP, une mesure étendue sera acquise avec cette requête.

| Données collectées | Description | Exemple |
|---|---|---|
| v_pn= | Valeur associée à la variable de chaîne de requête v_pn | v_pn=Formulaire d’application |

