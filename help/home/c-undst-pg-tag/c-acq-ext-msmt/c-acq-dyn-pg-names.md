---
description: Pour certains sites, il est nécessaire d’utiliser des requêtes d’objet incorporées pour transmettre des informations au serveur web afin que les détails sur la page réellement diffusée puissent être acquis par Capteur et utilisés pour la création de rapports et l’analyse.
title: Acquisition des noms de page dynamiques
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
exl-id: cd94caf0-b0dc-46c1-8f59-3ebb2f703286
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 1%

---

# Acquisition des noms de page dynamiques{#acquiring-dynamic-page-names}

{{eol}}

Pour certains sites, il est nécessaire d’utiliser des requêtes d’objet incorporées pour transmettre des informations au serveur web afin que les détails sur la page réellement diffusée puissent être acquis par Capteur et utilisés pour la création de rapports et l’analyse.

Cela peut s’avérer nécessaire si l’URL de la page, telle qu’elle est vue par le serveur web, n’indique pas le contenu de la page affiché pour le navigateur. Ce cas résulte souvent de l’utilisation de systèmes de personnalisation ou de gestion de contenu dynamique dans lesquels le contenu réel diffusé dans une page est déterminé à la volée par l’URL, le cookie, les données associées et la logique applicative.

L’implémentation d’un objet incorporé pour recueillir des mesures supplémentaires doit avoir un impact minimal sur les performances globales de votre site. Adobe vous suggère d’incorporer un fichier JavaScript comme objet utilisé pour collecter les attributs étendus. (Notez qu’un fichier JavaScript peut être incorporé sans aucun impact potentiel sur la mise en page et la présentation de votre page web, en raison de l’utilisation d’une image incorporée.) Pour capturer précisément les informations transmises dans l’objet incorporé, Adobe suggère également l’utilisation d’un nom commun. À des fins d’attribution de noms, Adobe fait référence à cet objet en tant que [!DNL zig.js]. Le [!DNL zig.js] doit être créé dans le répertoire approprié d’un serveur web sur lequel [!DNL Sensor] est installé. Ce fichier doit exister pour que la requête ne renvoie pas de code d’erreur 404. Le contenu du fichier lui-même n’est pas important. Vous devez utiliser un fichier vierge nommé [!DNL zig.js] afin de minimiser le volume de trafic réseau généré par la demande.

Pour [!DNL Sensor] pour collecter un nom utilisable pour la page qui a été réellement diffusée, quelques lignes de code JavaScript doivent être ajoutées aux pages dynamiques dont vous souhaitez effectuer le suivi ou auxquelles vous souhaitez ajouter un nom de page unique. Ce code incorpore un fragment de code JavaScript dans la page, ce qui entraîne l’envoi d’une demande d’objet incorporé tertiaire au serveur web pendant le chargement de la page. Cette requête envoie des détails sur la page spécifique qui a été renvoyée au serveur web. Le nom de la page qui a été réellement diffusée est renvoyé au serveur web sous la forme d’une variable dans la chaîne de requête de l’objet incorporé (dans ce cas, JavaScript).

En règle générale, la requête d’objet incorporée dans chaque page de HTML de ce type doit se présenter comme suit :

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE
var v = {};
v["_pn"] = "Application Form";
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>

<noscript>
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>

<!-- END REFERENCE PAGE TAG-->
```

[!DNL Log=1] s’assure que [!DNL Sensor] enregistre la requête en dépit de la variable [!DNL Sensor] les règles de filtrage de type de contenu, telles que le filtrage des demandes JavaScript et d’image avant leur stockage. La variable v_pn déclarée identifie le nom du contenu réel de la page diffusé de sorte que [!DNL Site] connaît le nom de la page que le visiteur a réellement consultée. La valeur v_pn peut être établie manuellement ou par un autre script ou code d’application.

Une fois la valeur collectée, vous pouvez configurer le serveur Data Workbench pour qu’il utilise le contenu de la variable de chaîne de requête (paire nom=valeur, par exemple, v_pn=Formulaire d’application) annexé au [!DNL zag.gif] URI (par exemple, [!DNL https://www.mysite.com/pageserved.asp?v_pn=Application%20Form]), en tant qu’augmentation de la variable [!DNL zag.gif] URI. Outre les mesures de base acquises à chaque requête HTTP, une mesure étendue sera acquise avec cette requête.

| Données collectées | Description | Exemple |
|---|---|---|
| v_pn= | Valeur associée à la variable de chaîne de requête v_pn | v_pn=Formulaire d’application |
