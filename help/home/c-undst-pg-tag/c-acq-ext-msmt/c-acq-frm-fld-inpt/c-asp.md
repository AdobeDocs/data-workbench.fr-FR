---
description: Les pages Web sont souvent structurées à l'aide du langage de programmation ASP (Active Server Pages).
solution: Analytics
title: Informations spécifiques à ASP
topic: Data workbench
uuid: 552288cb-b775-4121-8869-322f2a26932b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informations spécifiques à ASP{#asp-specific-information}

Les pages Web sont souvent structurées à l&#39;aide du langage de programmation ASP (Active Server Pages).

ASP est une technologie Microsoft qui s&#39;exécute dans IIS (Internet Information Services). Lorsqu&#39;un navigateur demande un fichier ASP, IIS transmet la requête au moteur ASP. Le moteur ASP lit le fichier ASP, ligne par ligne, et exécute les scripts du fichier. Enfin, le fichier ASP est renvoyé au navigateur sous forme de code HTML brut. ASP fournit des objets RESPOND ou REQUEST qui, en plus d&#39;autres utilisations, permettent la réponse ou la requête des requêtes utilisateur ou des données envoyées à partir de formulaires HTML.

Dans certains cas, vous pouvez ne pas ajouter les valeurs entrées dans les formulaires à l’URL affichée dans la barre d’adresse du navigateur d’un utilisateur ou qui est consultable dans le code HTML lui-même. JavaScript côté serveur simple vous permet d’ajouter des noms de champ de formulaire et leurs valeurs respectives au fichier journal sans les rendre disponibles dans le navigateur de l’utilisateur ni les intégrer dans le fichier HTML. Pour capturer les valeurs de formulaire réelles saisies dans des formulaires particuliers de votre site Web, vous devez ajouter quelques lignes de code pour ajouter les valeurs de formulaire à la requête de journal.

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

Ce processus ajouterait les valeurs de formulaire telles que définies aux données de requête pour la [!DNL Form Processing] page. Dans les données du journal, les valeurs ajoutées seraient disponibles sous forme de chaînes de requête de la [!DNL Form Processing] page, comme illustré ci-dessous. Par exemple, v_1, v_2, v_3 et v_4 sont désormais des chaînes de requête contenant les données saisies dans les champs de formulaire appropriés. La syntaxe décrite dans l’exemple ci-dessus peut être dupliquée pour tous les champs et valeurs de formulaire supplémentaires que vous souhaitez capturer.

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Si vous souhaitez que chaque champ et valeur de formulaire soit capturés et disponible pour l’analyse, vous pouvez utiliser la syntaxe suivante :

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues); 
```

Cet exemple montre comment prendre tous les champs de formulaire présents dans le code HTML avec leurs valeurs respectives et les ajouter en tant que chaînes de requête à l&#39;entrée de journal de la [!DNL Form Processing] page. Notez que cela inclurait tous les champs masqués présents dans le formulaire.

Les données du journal seraient augmentées comme indiqué dans le tableau suivant :

| Données collectées | Description | Exemple |
|---|---|---|
| v_1 | Valeur associée à la chaîne de requête NAME | v_1=John Smith |
| v_2 | Valeur associée à la chaîne de requête CITY | v_2=Los Angeles |
| v_3 | Valeur associée à la chaîne de requête STATE | v_3=Californie |
| v_4 | Valeur associée à la chaîne de requête ZIP | v_4=90210 |

