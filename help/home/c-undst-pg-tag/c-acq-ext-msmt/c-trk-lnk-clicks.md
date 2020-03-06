---
description: Etapes utilisées pour faciliter la collecte des clics sur les liens grâce à l’utilisation de la balise de page de référence.
solution: Analytics
title: Suivi des clics sur les liens
topic: Data workbench
uuid: e4c492d2-9c90-4ed7-b997-6c50bdf98f93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Suivi des clics sur les liens{#tracking-link-clicks}

Etapes utilisées pour faciliter la collecte des clics sur les liens grâce à l’utilisation de la balise de page de référence.

Grâce au déploiement de [!DNL Reference Page Tag], il est possible de collecter des données de mesure indiquant les liens (ou les valeurs href) sur lesquels les visiteurs cliquent lors de la visite de pages particulières. En règle générale, cette collection n’implique pas l’implémentation d’identifiants de lien supplémentaires dans vos pages HTML.

Pour faciliter la collecte des clics sur les liens via l’utilisation de la [!DNL Reference Page Tag], procédez comme suit :

1. Copiez le code suivant dans le fichier existant nommé [!DNL zig.js]:

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

1. Créez ou importez le fichier image 1 pixel par 1 pixel nommé [!DNL zag2.gif] dans un répertoire présent sur votre serveur Web.
1. Modifiez la [!DNL lc.src] variable pour référencer le domaine approprié de votre site Web à partir duquel le [!DNL zag2.gif]fichier est référencé.

1. Assurez-vous que les en-têtes de contrôle du cache appropriés sont définis pour les [!DNL zag.gif] fichiers et [!DNL zig.js] les fichiers.

1. Dans les fichiers HTML à partir desquels vous souhaitez collecter les valeurs de clic sur les liens, vous [!DNL Reference Page Tag Execution Call] devez modifier la variable pour informer la [!DNL Page Tag Execution Script] afin de capturer les clics sur les liens de cette page. Pour ce faire, remplacez la valeur de variable vlc par &quot;1&quot;, comme indiqué dans l’exemple de code suivant :

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
| v_ln= | Valeur désignant la campagne d’impression | v_ln=&quot;À propos de%20Us&quot; |

