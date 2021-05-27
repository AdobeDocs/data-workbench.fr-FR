---
description: Si les pare-feu réseau n’empêchent pas l’accès au serveur de répéteur à partir des ordinateurs Insight, vous pouvez créer une connexion entre le serveur de répéteur et Insight afin de pouvoir gérer le serveur de répéteur à l’aide d’Insight.
title: Création d’une connexion entre Insight et Répéteur
uuid: dccce83a-8708-4763-a19a-64d905a9f624
exl-id: 81e81db5-0517-41d4-a958-d08cd3975096
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 4%

---

# Création d’une connexion entre Insight et Répéteur{#creating-a-connection-between-insight-and-repeater}

Si les pare-feu réseau n’empêchent pas l’accès au serveur de répéteur à partir des ordinateurs Insight, vous pouvez créer une connexion entre le serveur de répéteur et Insight afin de pouvoir gérer le serveur de répéteur à l’aide d’Insight.

**Pour créer une connexion entre  [!DNL Insight] et le serveur de répéteur**

1. Dans [!DNL Insight], dans l’onglet [!DNL Admin], cliquez sur la miniature **[!UICONTROL Configure Connections to Servers]** pour ouvrir l’espace de travail Configurer les connexions aux serveurs .
1. Dans la fenêtre [!DNL Insight.cfg], cliquez avec le bouton droit de la souris sur **[!UICONTROL Servers]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Server]**.
1. Pour le nouveau serveur, renseignez les paramètres suivants :

<table id="table_DD79587255134B5A888A0F57CF10E5B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour ce paramètre... </th> 
   <th colname="col2" class="entry"> Spécifiez les... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom </td> 
   <td colname="col2">(Facultatif) Nom que vous souhaitez utiliser pour représenter le serveur de répéteur dans son interface utilisateur. <span class="keyword"> Insight</span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse </td> 
   <td colname="col2"> <p>Nom d’hôte ou adresse IP numérique de votre serveur de répéteur. </p> <p>Exemple : <span class="filepath"> Répéteur.mycompany.com</span> ou 192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificat client SSL </td> 
   <td colname="col2"> <p>Facultatif, sauf si vous disposez de plusieurs certificats. Nom du fichier contenant le certificat numérique pour cette copie de <span class="keyword"> Insight</span>. (Il s’agit du fichier que vous avez téléchargé lors de l’installation de <span class="keyword"> Insight</span>.) </p> <p>Exemple : <span class="filepath"> Samantha Smith.pem</span></p> <p>Si vous laissez ce paramètre vide, <span class="keyword"> Insight</span> utilise n’importe quel certificat présent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveur SSL </p> <p>Nom commun </p> </td> 
   <td colname="col2">Nom commun attribué au serveur de répéteur. Ce nom doit correspondre au nom commun attribué au serveur de répéteur dans son certificat de licence. Si vous avez accès au fichier de certificat du répéteur (<span class="filepath"> Certificats\server_cert.pem</span>), vous pouvez trouver le nom commun en ouvrant le fichier avec un éditeur de texte tel que Notepad. Le nom commun est identifié dans le champ CN du certificat. </td> 
  </tr> 
 </tbody> 
</table>

1. Enregistrez le fichier en cliquant avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre et en cliquant sur **[!UICONTROL Save]**. [!DNL Insight] tentera de vous connecter au serveur de répéteur à l’aide des paramètres que vous avez spécifiés. Si une connexion est établie, une icône de serveur verte s’affiche dans l’interface [!DNL Servers Manager]. Si une connexion ne peut pas être établie, une icône rouge s’affiche.

   Pour plus d’informations sur l’interface [!DNL Servers Manager], consultez le * [!DNL Insight] Guide de l’utilisateur*.
