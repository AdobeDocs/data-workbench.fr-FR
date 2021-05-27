---
description: Dans le cadre des données de mesure de base collectées, Capteur collecte les cookies de domaine envoyés depuis l’ordinateur du visiteur lors de l’exécution d’une requête auprès de votre serveur web.
title: Acquisition des données de mesures par des cookies
uuid: 34cd6baf-6317-4774-8165-58208698b53c
exl-id: 37c7b5f6-33bf-4373-963a-e08a826e05df
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 2%

---

# Acquisition des données de mesures par des cookies{#acquiring-measurement-data-through-cookies}

Dans le cadre des données de mesure de base collectées, Capteur collecte les cookies de domaine envoyés depuis l’ordinateur du visiteur lors de l’exécution d’une requête auprès de votre serveur web.

Cela inclut les cookies de session et persistants définis sur votre site web lorsqu’un visiteur interagit avec votre système.

Dans la plupart des cas, les sites web définissent des cookies persistants pour identifier les visiteurs ou capturer les entrées utilisateur à utiliser au cours des sessions suivantes du visiteur. Toutes les informations écrites et stockées dans des cookies persistants peuvent être capturées et utilisées avec toutes les autres données de mesure du serveur Data Workbench.

Un exemple de cookie persistant de ce type peut impliquer un identifiant de client sous la forme d’une clé numérique présente dans un cookie spécifique au domaine résidant sur l’ordinateur du visiteur. Outre l’identification de l’utilisateur en tant que visiteur récurrent, le cookie persistant peut également être utilisé pour identifier davantage le visiteur en tant que client récurrent ou pour lier le visiteur aux informations contenues dans une base de données client afin de permettre l’affichage d’informations démographiques client hors ligne dans [!DNL Site] et leur utilisation dans le cadre d’une analyse interactive.

Les cookies de session peuvent être un bon mécanisme pour collecter les entrées utilisateur par le biais de champs de formulaire ou d’autres éléments interactifs dynamiques dans votre site web. Dans le cas d’un site web implémentant des formulaires pour capturer des données d’entrée spécifiques à l’utilisateur, les informations restent dans le cookie de session uniquement tant que la session est principale. Lorsqu’un utilisateur quitte votre site web ou met fin à une session, les informations ne sont plus stockées sur l’ordinateur de l’utilisateur. Toutefois, les informations saisies sont capturées par [!DNL Sensor] et mises à disposition sous forme de données de mesure dans [!DNL Site].

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

Dans cet exemple, une fonction est appelée pour définir un cookie de session sur l’ordinateur du visiteur avec le nom du champ et la valeur saisie dans le champ de formulaire. Lorsque le formulaire est envoyé et que la page web suivante est demandée, le jeu de cookies de session est transmis au serveur web et collecté par [!DNL Sensor]. Les données suivantes sont donc disponibles dans le serveur Data Workbench pour une utilisation dans l’analyse des données :

| Données collectées | Description | Exemple |
|---|---|---|
| v_1 | Valeur associée au cookie v_1. Cette valeur représente le NOM saisi dans le champ de formulaire, qui a entraîné la définition du cookie de session. | v_1=John Smith |

Les cookies de session peuvent également être utilisés pour capturer de manière itérative des champs de formulaire ou une multitude de variables JavaScript incorporées présentes dans une page HTML. Dans l’exemple suivant, JavaScript est utilisé pour capturer de manière récursive tout champ de formulaire présent dans un fichier HTML et définir un cookie de session avec les paires nom=valeur appropriées.

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

Dans cet exemple, un cookie de session est défini sur l’ordinateur du visiteur avec le nom et la valeur de chaque champ de formulaire existant dans le formulaire. Cela inclut les champs de saisie, les cases à cocher, les boutons radio, les cases à cocher et les zones de texte. Comme vous pouvez le constater dans cet exemple, comme le nombre de champs de formulaire est inconnu, il est nécessaire de capturer toutes les valeurs de nom et de champ de formulaire sous la forme d’une seule chaîne, délimitée par une esperluette. Cette étape doit être effectuée en raison d’une limite du nombre de cookies qu’un utilisateur peut avoir sur son ordinateur à un moment donné. Microsoft Internet Explorer permet à seulement vingt (20) cookies de session d’être présents avant de déposer l’ancien.
