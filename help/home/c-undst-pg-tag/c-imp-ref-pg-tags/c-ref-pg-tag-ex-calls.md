---
description: L’appel d’exécution de balise de page de référence est inséré dans des pages web pour lesquelles vous souhaitez collecter des données de mesure.
title: Ajouter des appels d’exécution de balise de page de référence
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
exl-id: a4f9ab2b-50e8-4e0b-9c87-80dffb697316
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 3%

---

# Ajouter des appels d’exécution de balise de page de référence{#adding-reference-page-tag-execution-calls}

L’appel d’exécution de balise de page de référence est inséré dans des pages web pour lesquelles vous souhaitez collecter des données de mesure.

Il doit être inclus dans le corps du document HTML et peut être placé dans un pied de page d’inclusion global, le cas échéant. [!DNL Reference Page Tag Execution Call] peut être modifié par votre équipe pour collecter des informations supplémentaires qui peuvent être identifiées lors des réunions de collecte des exigences avec l’équipe des services de conseil d’Adobe.

Pour faciliter la collecte de données par l’utilisation de la balise [!DNL Reference Page Tag], procédez comme suit :

1. Copiez le code suivant dans le corps de votre document HTML :

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

1. Modifiez le chemin d’accès à l’emplacement des fichiers [!DNL zig.js] et [!DNL zag.gif]. Par exemple :

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

Assurez-vous que les en-têtes HTTP de contrôle du cache appropriés ont été définis sur votre serveur web pour vous assurer que les fichiers [!DNL zig.js]et [!DNL zag.gif] ne sont pas mis en cache par le navigateur. Vous pouvez définir les informations de l’en-tête HTTP Cache-Control à l’aide de l’une des deux méthodes suivantes. La première méthode consiste à définir un en-tête HTTP via le serveur web. La deuxième méthode consiste à définir un en-tête HTTP pour chaque page ou objet incorporé spécifique à l’aide d’un script. Avec la méthode de script, la page web doit avoir été créée à l’aide d’un langage de programmation tel que JSP ou ASP. La page est ensuite scénarisée afin d’envoyer les informations d’en-tête appropriées. Deux inconvénients évidents accompagnent cette méthode : 1) toutes les pages doivent être codées pour envoyer l’en-tête, et 2) les pages ne peuvent pas être du code HTML statique, ce qui a un effet sur les performances du serveur web.

Les sites web s’exécutant sur Microsoft IIS peuvent ajouter l’en-tête HTTP approprié via la console de gestion Microsoft. Les sites web diffusés à partir des serveurs web Netscape iPlanet peuvent y parvenir en modifiant le fichier [!DNL obj.conf] dans le répertoire de configuration du site. Le serveur web Apache permet aux webmasters de personnaliser les en-têtes HTTP à l’aide du module mod_headers inclus, où AOLServer devient personnalisable grâce à l’utilisation des modules Tcl. Avant d’implémenter des en-têtes HTTP Cache-Control, vous devez vous référer à la documentation spécifique à votre plateforme de serveur web.

En règle générale, l’en-tête HTTP doit être structuré comme suit :

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```
