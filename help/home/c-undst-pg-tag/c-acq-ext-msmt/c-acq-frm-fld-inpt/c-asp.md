---
description: Les pages web sont souvent structurées à l’aide du langage de programmation ASP (Principal Server Pages).
title: Informations spécifiques à ASP
uuid: 552288cb-b775-4121-8869-322f2a26932b
exl-id: f73235e1-d44a-4056-b1f4-a86879c19483
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# Informations spécifiques à ASP{#asp-specific-information}

Les pages web sont souvent structurées à l’aide du langage de programmation ASP (Principal Server Pages).

ASP est une technologie Microsoft qui s’exécute dans IIS (Internet Information Services). Lorsqu’un navigateur demande un fichier ASP, IIS transmet la demande au moteur ASP. Le moteur ASP lit le fichier ASP ligne par ligne et exécute les scripts du fichier. Enfin, le fichier ASP est renvoyé au navigateur en tant que HTML brut. ASP fournit des objets RESPOND ou REQUEST qui, en plus d’autres utilisations, permettent la réponse ou la requête des requêtes utilisateur ou des données envoyées à partir de formulaires de HTML.

Dans certains cas, vous pouvez ne pas ajouter les valeurs saisies dans les formulaires à l’URL affichée dans la barre d’adresse du navigateur d’un utilisateur ou visible dans le code de HTML lui-même. Le JavaScript côté serveur simple vous permet d’ajouter des noms de champ de formulaire et leurs valeurs respectives au fichier journal sans les rendre disponibles dans le navigateur de l’utilisateur ni les incorporer dans le fichier de HTML. Pour capturer les valeurs de formulaire réelles saisies dans des formulaires spécifiques de votre site web, quelques lignes de code doivent être ajoutées pour ajouter les valeurs de formulaire à la requête de journal.

Dans la page de traitement d’un formulaire, incluez le code suivant pour ajouter les valeurs de formulaire saisies aux données de requête (en plus d’écrire les valeurs de formulaire envoyées dans une base de données externe ou à un autre emplacement) :

```
var sName= Request.Form("Name");
var sCity= Request.Form("City");
var sState= Request.Form("State");
var sZip= Request.Form("Zip");

Response.AppendToLog("&v_1=" +  sName);
Response.AppendToLog("&v_2=" +  sCity);
Response.AppendToLog("&v_3=" +  sState);
Response.AppendToLog("&v_4=" +  sZip);
```

Ce processus ajoute les valeurs de formulaire telles que définies aux données de requête de la page [!DNL Form Processing]. Dans les données du journal, les valeurs ajoutées seraient disponibles sous forme de chaînes de requête de la page [!DNL Form Processing] comme illustré ci-dessous. Par exemple, v_1, v_2, v_3 et v_4 seront désormais des chaînes de requête contenant les données saisies dans les champs de formulaire appropriés. La syntaxe décrite dans l’exemple ci-dessus peut être dupliquée pour les champs et valeurs de formulaire supplémentaires que vous souhaitez capturer.

```
https://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Si vous souhaitez que chaque champ et valeur de formulaire soit capturés et disponible pour analyse, vous pouvez utiliser la syntaxe suivante :

```
var formvalues = Response.Form;
Response.AppendToLog(formvalues);
```

Cet exemple prend tous les champs de formulaire présents dans le HTML avec leurs valeurs respectives et les ajoute en tant que chaînes de requête à l’entrée de journal de la page [!DNL Form Processing]. Notez que cela inclut tous les champs masqués présents dans le formulaire.

Les données du journal seraient augmentées comme décrit dans le tableau suivant :

| Données collectées | Description | Exemple |
|---|---|---|
| v_1 | Valeur associée à la chaîne de requête NAME | v_1=John Smith |
| v_2 | Valeur associée à la chaîne de requête CITY | v_2=Los Angeles |
| v_3 | Valeur associée à la chaîne de requête STATE | v_3=Californie |
| v_4 | Valeur associée à la chaîne de requête ZIP | v_4=90210 |
