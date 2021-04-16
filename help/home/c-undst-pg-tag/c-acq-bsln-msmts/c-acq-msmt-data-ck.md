---
description: Dans le cadre des données de mesure de référence collectées, Sensor collecte les cookies de domaine envoyés depuis l’ordinateur d’un visiteur lors d’une demande auprès de votre serveur Web.
title: Acquisition des données de mesures par des cookies
uuid: 34cd6baf-6317-4774-8165-58208698b53c
exl-id: 37c7b5f6-33bf-4373-963a-e08a826e05df
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 2%

---

# Acquisition des données de mesures par des cookies{#acquiring-measurement-data-through-cookies}

Dans le cadre des données de mesure de référence collectées, Sensor collecte les cookies de domaine envoyés depuis l’ordinateur d’un visiteur lors d’une demande auprès de votre serveur Web.

Cela inclut les cookies persistants et de session que votre site Web définit lorsqu’un visiteur interagit avec votre système.

Dans la plupart des cas, les sites Web définissent des cookies persistants afin d’identifier les visiteurs ou de capturer les entrées des utilisateurs en vue de les utiliser au cours des sessions de visiteur suivantes. Toute information écrite et stockée dans des cookies persistants peut être capturée et utilisée avec toutes les autres données de mesure du serveur de l’outil de données.

Un exemple de cookie persistant de ce type peut impliquer un identifiant de client sous la forme d’une clé numérique présente dans un cookie spécifique au domaine résidant sur l’ordinateur du visiteur. Outre l’identification de l’utilisateur en tant que visiteur de retour, le cookie persistant peut également être utilisé pour identifier le visiteur en tant que client de retour ou pour lier le visiteur aux informations contenues dans une base de données de clients afin de permettre l’affichage des informations démographiques des clients hors ligne dans [!DNL Site] et leur utilisation pour l’analyse interactive.

Les cookies de session peuvent être un bon mécanisme de collecte des données utilisateur par le biais de champs de formulaire ou d’autres éléments interactifs dynamiques dans votre site Web. Dans le cas d’un site Web qui met en oeuvre des formulaires pour capturer des données d’entrée spécifiques à l’utilisateur, les informations restent dans le cookie de session tant que la session est principale. Lorsqu’un utilisateur quitte votre site Web ou termine une session par la suite, les informations ne sont plus stockées sur l’ordinateur de l’utilisateur. Cependant, les informations saisies sont capturées par [!DNL Sensor] et mises à disposition sous forme de données de mesure dans [!DNL Site].

Voici un exemple d’utilisation d’un cookie de session pour capturer une variable de formulaire unique entrée par un visiteur.

```
<html> 
<head> 
<title>Cookie Collection </title> 
 
<script language="JavaScript"> 
function AppendFormValues() 
{ 
 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
document.cookie = cookie; 
 
testform.submit(); 
 
} 
</script> 
</head> 
<body> 
<form name="testform" method="post" action="nextpage.asp"> 
<input type="text" size=15 name="name"><br />enter name 
<br><br> 
 
<a href="javascript:AppendFormValues();">Click Here To </a><br /><br /> 
<br /><br /><br /> 
 
</body> 
</html> 
```

Dans cet exemple, une fonction est appelée pour définir un cookie de session sur l’ordinateur du visiteur avec le nom du champ et la valeur saisie dans le champ de formulaire. Lorsque le formulaire est envoyé et que la page Web suivante est demandée, le jeu de cookies de session est transmis au serveur Web et collecté par [!DNL Sensor]. Les données suivantes sont donc disponibles dans le serveur de l’outil de données pour une utilisation dans l’analyse des données :

| Données collectées | Description | Exemple |
|---|---|---|
| v_1 | Valeur associée au cookie v_1. Cette valeur représente le NOM entré dans le champ de formulaire qui a déclenché la définition du cookie de session. | v_1=John Smith |

Les cookies de session peuvent également être utilisés pour capturer de manière itérative des champs de formulaire ou une multitude de variables JavaScript incorporées présentes dans une page HTML. Dans l’exemple suivant, JavaScript est utilisé pour capturer de manière récursive tout champ de formulaire présent dans un fichier HTML et pour définir un cookie de session avec les paires nom=valeur appropriées.

```
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
var cookie="formcookie="; 
for (i=0; i<document.testform.length; i++){ 
if (document.testform.elements[i].type =="radio") {            
if (document.testform.elements[i].checked){ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
else if (document.testform.elements[i].type =="select") { 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var optionindex = eval(document.testform.elements[i].selectedIndex); 
var formvalue = document.testform.elements[i].options[optionindex].value;             
cookie += formitem + "=" + formvalue + "&"; 
} 
else{ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
document.cookie = cookie; 
document.testform.submit(); 
} 
 
</script>
```

Dans cet exemple, un cookie de session est défini sur l’ordinateur du visiteur avec le nom et la valeur de chaque champ de formulaire existant dans le formulaire. Cela inclut les champs de saisie, les cases à cocher, les boutons radio, les cases à cocher et les zones de texte. Comme vous pouvez le constater dans cet exemple, étant donné que le nombre de champs de formulaire est inconnu, il est nécessaire de capturer toutes les valeurs de nom et de champ de formulaire sous la forme d’une chaîne unique, délimitée par une esperluette. Cette étape doit être effectuée en raison d’une limite du nombre de cookies qu’un utilisateur peut avoir sur son ordinateur à un moment donné. Microsoft Internet Explorer n&#39;autorise la présence que de vingt (20) cookies de session avant qu&#39;il ne commence à abandonner le plus ancien.
