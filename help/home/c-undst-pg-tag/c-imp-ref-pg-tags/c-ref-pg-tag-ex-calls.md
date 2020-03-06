---
description: L’appel d’exécution des balises de page de référence est inséré dans les pages Web pour lesquelles vous souhaitez collecter des données de mesure.
solution: Analytics
title: Ajout d’appels d’exécution de balises de page de référence
topic: Data workbench
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Ajout d’appels d’exécution de balises de page de référence{#adding-reference-page-tag-execution-calls}

L’appel d’exécution des balises de page de référence est inséré dans les pages Web pour lesquelles vous souhaitez collecter des données de mesure.

Il doit être inclus dans le corps du document HTML et peut être placé dans un pied de page d’inclusion global, le cas échéant. L’équipe [!DNL Reference Page Tag Execution Call] peut la modifier afin de collecter des informations supplémentaires susceptibles d’être identifiées lors de réunions de collecte des besoins avec l’équipe Adobe Consulting Services.

Pour faciliter la collecte de données par l’utilisation de la [!DNL Reference Page Tag], procédez comme suit :

1. Copiez le code suivant dans le corps du document HTML :

   ```
   <!--//BEGIN REFERENCE PAGE TAG--> 
   <script language="javascript"> 
   var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
   var v = {}; 
   </script> 
   
   <!--//MODIFIY PATH TO ZIG.JS--> 
   <script language="javascript" src="/path/to/zig.js" type="text/javascript"></script> 
   <!--//END REFERENCE PAGE TAG--> 
   
   <noscript> 
   <img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
   </noscript> 
   <!-- END REFERENCE PAGE TAG-->
   ```

1. Modifiez le chemin d’accès à l’emplacement des fichiers [!DNL zig.js] et [!DNL zag.gif] . Par exemple :

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

Assurez-vous que les en-têtes HTTP Cache-Control appropriés ont été définis sur votre serveur Web pour vous assurer que les fichiers [!DNL zig.js]et [!DNL zag.gif] les fichiers ne sont pas mis en cache par le navigateur. Vous pouvez définir les informations d’en-tête HTTP Cache-Control à l’aide de l’une des deux méthodes suivantes. La première méthode consiste à définir un en-tête HTTP via le serveur Web. La deuxième méthode consiste à définir un en-tête HTTP pour chaque page ou objet incorporé spécifique à l’aide d’un script. Avec la méthode de script, la page Web doit avoir été créée à l’aide d’un langage de programmation tel que JSP ou ASP. La page est ensuite scriptée afin d’envoyer les informations d’en-tête appropriées. Deux inconvénients évidents accompagnent cette méthode : 1) toutes les pages doivent être codées pour envoyer l’en-tête, et 2) les pages ne peuvent pas être du code HTML statique, ce qui a un effet sur les performances du serveur Web.

Les sites Web s&#39;exécutant sur Microsoft IIS peuvent ajouter l&#39;en-tête HTTP approprié via la console de gestion Microsoft. Les sites Web fournis par les serveurs Web Netscape iPlanet peuvent y parvenir en modifiant le [!DNL obj.conf] fichier dans le répertoire de configuration du site. Le serveur Web Apache permet aux webmasters de personnaliser les en-têtes HTTP à l&#39;aide du module mod_headers inclus, où AOLServer devient personnalisable à l&#39;aide des modules Tcl. Avant d’implémenter les en-têtes HTTP Cache-Control, vous devez vous reporter à la documentation spécifique à votre plateforme de serveur Web.

En général, l’en-tête HTTP doit être structuré comme suit :

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```

