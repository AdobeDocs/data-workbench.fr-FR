---
description: Procédure à suivre pour faciliter la collecte des clics sur les liens en utilisant la balise de page de référence.
title: Suivi des clics sur les liens
uuid: e4c492d2-9c90-4ed7-b997-6c50bdf98f93
exl-id: 0cb743e6-5c6e-4f80-bc77-83d1e706c92b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 3%

---

# Suivi des clics sur les liens{#tracking-link-clicks}

Procédure à suivre pour faciliter la collecte des clics sur les liens en utilisant la balise de page de référence.

Grâce au déploiement de [!DNL Reference Page Tag], il est possible de collecter des données de mesure indiquant les liens (ou les valeurs href) sur lesquels les visiteurs cliquent lors de la visite de pages particulières. En règle générale, cette collection n’implique pas l’implémentation d’identifiants de lien supplémentaires dans vos pages HTML.

Pour faciliter la collecte des clics sur les liens grâce à l’utilisation de [!DNL Reference Page Tag], procédez comme suit :

1. Copiez le code suivant dans le fichier existant nommé [!DNL zig.js] :

   ```
   //REFERENCE LINK AND FORM CLICK PAGE TAG 
   //INITIATE FUNCTIONS ONLOAD 
   function addEvent(obj, evType, fn){  
    if (obj.addEventListener){  
      obj.addEventListener(evType, fn, false);  
      return true;  
    } else if (obj.attachEvent){  
      var r = obj.attachEvent("on"+evType, fn);  
      return r;  
    } else {  
      return false;  
    }  
   } 
   addEvent(window, 'load', startCapture); 
   addEvent(window, 'load', startCapture); 
   function startCapture(){ 
   //TO CAPTURE LINK CLICKS 
     if (vlc == "1"){captureLink();} 
     //TO CAPTURE FORM FIELD CLICKS 
     if (vfc == "1"){captureForm();} 
   } 
   //BEGIN LINK CAPTURE PAGE TAG 
   function captureLink(){ 
     if (document.links[0]){ 
       if (document.links){ 
         var links = document.links, link, k=0; 
         while(link=links[k++]) { 
           link.onclick = captureLinkName; 
    } 
       } 
     } 
   } 
   function captureLinkName() { 
     var lc=new Image(); 
     this.parent = this.parentNode; 
     lc.src='zag2.gif?linkname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END LINK CAPTURE PAGE TAG 
   //BEGIN FORM CLICK CAPTURE PAGE TAG 
   function captureForm(){ 
     if (document.forms[0]) { 
       if(document.forms){ 
    for(i=0; i<document.forms[0].elements.length; i++){ 
           var forms = document.forms[0].elements[i]; 
           forms.onfocus = captureFormName; 
         } 
       } 
     } 
   } 
   function captureFormName() { 
     var fc=new Image(); 
     fc.src='zag3.gif?fieldname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END FORM CLICK CAPTURE PAGE TAG
   ```

1. Créez ou placez le fichier image de 1 pixel par 1 nommé [!DNL zag2.gif] dans un répertoire présent sur votre serveur web.
1. Modifiez la variable [!DNL lc.src] afin de référencer le domaine approprié de votre site web à partir duquel le fichier [!DNL zag2.gif]est référencé.

1. Assurez-vous que les en-têtes de contrôle du cache appropriés sont définis pour les fichiers [!DNL zag.gif] et [!DNL zig.js].

1. Dans les fichiers HTML à partir desquels vous souhaitez collecter les valeurs de clic sur les liens, la balise [!DNL Reference Page Tag Execution Call] doit être modifiée pour informer la balise [!DNL Page Tag Execution Script] afin de capturer les clics sur les liens pour cette page. Pour ce faire, remplacez la valeur de la variable vlc par &quot;1&quot;, comme indiqué dans l’exemple de code suivant :

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "1" //Capture Link Click  1=TRUE, 0=FALSE 
var vfc = "0"; //Capture Form Field Click  1=TRUE, 0=FALSE 
var v = {}; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

| Données collectées | Description | Exemple |
|---|---|---|
| v_ln= | Valeur désignant la campagne d’impression | v_ln=&quot;About%20Us&quot; |
