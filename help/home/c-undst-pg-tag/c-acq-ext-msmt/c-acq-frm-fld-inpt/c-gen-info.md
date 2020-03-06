---
description: Les valeurs saisies dans un formulaire d’une page Web peuvent être collectées et ajoutées à la chaîne de requête de la page demandée ultérieurement (lors de l’envoi du formulaire) par le biais de JavaScript.
solution: Analytics
title: Informations générales
topic: Data workbench
uuid: 401816a5-1d95-48e6-bedf-ee2a5dbd2d50
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informations générales{#general-information}

Les valeurs saisies dans un formulaire d’une page Web peuvent être collectées et ajoutées à la chaîne de requête de la page demandée ultérieurement (lors de l’envoi du formulaire) par le biais de JavaScript.

Ceci est illustré dans l’exemple suivant. Incluez ce code JavaScript après tout script de validation de formulaire utilisé dans vos pages HTML.

```
<html> 
<head> 
</head> 
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
for(var i = 0; i < document.formname.length; i++) 
{ 
var item = document.formname.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
formvalues += formitem + '=' + formvalue + '&'; 
} 
document.formname.action = document.formname.action + '?' + formvalues; 
 
} 
</script> 
<body> 
<form name="formname" action="thankyou.asp" method="POST" onSubmit="AppendFormValues();"> 
<input name="NAME" size="50" value=""></input>name<br/> 
<input name="CITY" size="50" value=""></input>city<br/> 
<input name="STATE" size="50" value=""></input>state<br/> 
<input name="ZIP" size="10" value=""></input>zip<br /> 
<input type="submit" name="submit" value="submit"/> 
</body> 
</html> 
```

Cet exemple montre comment ajouter les valeurs saisies dans le formulaire par l&#39;utilisateur du navigateur à la page &quot;thankyou.asp&quot; suivante, indiquée dans la valeur Action de formulaire, comme suit :

```
http://www.myserver.com/thankyou.asp?v_1=John Smith&v_2=Los Angeles&v_3=California&v_4=90210
```

Les mesures étendues suivantes seraient obtenues avec cette demande en plus des mesures de base recueillies par [!DNL Sensor]:

| Données collectées | Description | Exemple |
|---|---|---|
| v_1 | Valeur associée au champ de formulaire NAME | v_1=John Smith |
| v_2 | Valeur associée au champ de formulaire CITY | v_2=Los Angeles |
| v_3 | Valeur associée au champ de formulaire STATE | v_3=Californie |
| v_4 | Valeur associée au champ de formulaire ZIP | v_4=90210 |

