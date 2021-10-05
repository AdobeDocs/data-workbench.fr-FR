---
description: Les valeurs saisies dans un formulaire dans une page web peuvent être collectées et ajoutées dans la chaîne de requête de la page demandée ultérieurement (lors de l’envoi du formulaire) à l’aide de JavaScript.
title: Informations générales
uuid: 401816a5-1d95-48e6-bedf-ee2a5dbd2d50
exl-id: 9effc72b-e75f-423c-87ec-6ac25edee8d6
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 3%

---

# Informations générales{#general-information}

Les valeurs saisies dans un formulaire dans une page web peuvent être collectées et ajoutées dans la chaîne de requête de la page demandée ultérieurement (lors de l’envoi du formulaire) à l’aide de JavaScript.

Ceci est illustré dans l’exemple suivant. Insérez ce code JavaScript après tout script de validation de formulaire utilisé dans vos pages de HTML.

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

Cet exemple ajoute les valeurs saisies dans le formulaire par l’utilisateur du navigateur à la page &quot;thankyou.asp&quot; suivante indiquée dans la valeur Action de formulaire comme suit :

```
https://www.myserver.com/thankyou.asp?v_1=John Smith&v_2=Los Angeles&v_3=California&v_4=90210
```

Les mesures étendues suivantes seraient acquises avec cette demande en plus des mesures de base collectées par [!DNL Sensor] :

| Données collectées | Description | Exemple |
|---|---|---|
| v_1 | Valeur associée au champ de formulaire NAME | v_1=John Smith |
| v_2 | Valeur associée au champ de formulaire CITY | v_2=Los Angeles |
| v_3 | Valeur associée au champ de formulaire STATE | v_3=Californie |
| v_4 | Valeur associée au champ de formulaire ZIP | v_4=90210 |
