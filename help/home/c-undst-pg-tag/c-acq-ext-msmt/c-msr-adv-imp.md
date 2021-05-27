---
description: Le marketing de votre site web peut impliquer le placement de publicités sous forme d’images ou d’autres fichiers multimédias enrichis (diffusés à partir de votre serveur web) sur des sites web tiers.
title: Mesure de l’impression de publicités
uuid: ca2bd6bf-4f49-406c-b47a-18d6abfb48a4
exl-id: 77cd816e-63a4-4080-ac65-0661e1de4ec0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 4%

---

# Mesure de l’impression de publicités{#measuring-advertisement-impression}

Le marketing de votre site web peut impliquer le placement de publicités sous forme d’images ou d’autres fichiers multimédias enrichis (diffusés à partir de votre serveur web) sur des sites web tiers.

Dans ce cas, vous pouvez mesurer à la fois l’impression de la publicité sur un navigateur et le clic publicitaire ultérieur, le cas échéant, sur l’URL cible de la publicité sur votre site web.

Pour les publicités sous forme d’images, l’ajout de [!DNL Log=1] à la chaîne de requête entraîne la demande d’image, et donc l’impression de la publicité, capturée par [!DNL Sensor] à des fins d’analyse.

```
<!—REFERENCE IMPRESSION TAG-> 
<IMG SRC="http://www.mysite.com/images/zag.gif?Log=1&v_ic=CAMPAIGN 1&v_ica=72890ab&v_icr=http://money.cnn.com/markets/"/>
<!--END REFERENCE IMPRESSION TAG-->
```

| Données collectées | Description | Exemple |
|---|---|---|
| v_ic= | Valeur désignant la campagne d’impression | v_ic=&quot;CAMPAIGN1&quot; |
| v_ica= | Valeur désignant la ressource de campagne d’impression | v_ica=&quot;72890ab&quot; |
| v_icr= | Valeur désignant le référent de campagne d’impression | v_icr=&quot;http://money.cnn.com/markets/ |

Outre l’ajout de [!DNL Log=1] à la demande d’image, un identifiant doit être ajouté à l’URL qui mène de la publicité à la page cible de votre site web pour suivre la publicité qui a conduit au clic publicitaire et pour suivre le clic publicitaire à nouveau dans la campagne spécifique pour cette publicité.

```
<a href=”www.mysite.com/path/to/landingpage?Log=1&v_c=CAMPAIGN&v_ca=72890ab&v_cr=http://money.cnn.com/markets/”>
Click Here
</a>
```

<table id="table_B87134C522EF4AC9BD2AFA6F4A0CF574"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Données collectées </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Exemple </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> v_c= </td> 
   <td colname="col2"> Valeur désignant la campagne de clic publicitaire </td> 
   <td colname="col3"> v_c="CAMPAIGN1" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_ca= </td> 
   <td colname="col2"> Valeur désignant la ressource de campagne de clic publicitaire </td> 
   <td colname="col3"> v_ca="72890ab" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_cr= </td> 
   <td colname="col2"> Valeur désignant le référent de campagne de clic publicitaire </td> 
   <td colname="col3"> <p> <span class="filepath"> v_cr="http://money.cnn.com/</span> </p> <p>marchés/ </p> </td> 
  </tr> 
 </tbody> 
</table>
