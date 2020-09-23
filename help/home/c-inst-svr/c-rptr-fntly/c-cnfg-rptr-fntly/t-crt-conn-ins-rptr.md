---
description: Si les pare-feu réseau n’empêchent pas l’accès au serveur de répéteurs à partir des ordinateurs Insight, vous pouvez créer une connexion entre le serveur de répéteurs et Insight afin de pouvoir gérer le serveur de répéteurs à l’aide d’Insight.
solution: Analytics
title: Création d’une connexion entre Insight et Répéteur
uuid: dccce83a-8708-4763-a19a-64d905a9f624
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 4%

---


# Création d’une connexion entre Insight et Répéteur{#creating-a-connection-between-insight-and-repeater}

Si les pare-feu réseau n’empêchent pas l’accès au serveur de répéteurs à partir des ordinateurs Insight, vous pouvez créer une connexion entre le serveur de répéteurs et Insight afin de pouvoir gérer le serveur de répéteurs à l’aide d’Insight.

**Pour créer une connexion entre[!DNL Insight]et le serveur de répétition**

1. Dans [!DNL Insight]l’ [!DNL Admin] onglet, cliquez sur la **[!UICONTROL Configure Connections to Servers]** miniature pour ouvrir l’espace de travail Configurer les connexions aux serveurs.
1. Dans la [!DNL Insight.cfg] fenêtre, cliquez avec le bouton droit **[!UICONTROL Servers]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Server]**.
1. Pour le nouveau serveur, exécutez les paramètres suivants :

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
   <td colname="col2">(Facultatif) Nom que vous souhaitez utiliser <span class="keyword"> Insight</span> pour représenter le serveur de répéteurs dans son interface utilisateur. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adresse </td> 
   <td colname="col2"> <p>Nom d’hôte ou adresse IP numérique de votre serveur de répéteurs. </p> <p>Exemple : <span class="filepath"> Repeater.mycompany.com</span> ou 192.168.1.90 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificat client SSL </td> 
   <td colname="col2"> <p>Facultatif, sauf si vous disposez de plusieurs certificats. Nom du fichier contenant le certificat numérique pour cette copie d’ <span class="keyword"> Insight</span>. (Il s’agit du fichier que vous avez téléchargé lors de l’installation d’ <span class="keyword"> Insight</span>.) </p> <p>Exemple : <span class="filepath"> Samantha Smith.pem</span></p> <p>Si vous laissez ce paramètre vide, <span class="keyword"> Insight</span> utilise le certificat existant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveur SSL </p> <p>Nom commun </p> </td> 
   <td colname="col2">Nom commun attribué au serveur de répéteurs. Ce nom doit correspondre au nom commun attribué au serveur de répéteurs dans son certificat de licence. Si vous avez accès au fichier de certificat du répéteur (<span class="filepath"> Certificates\server_cert.pem</span>), vous pouvez trouver le nom commun en ouvrant le fichier avec un éditeur de texte tel que le Bloc-notes. Le nom commun est identifié dans le champ CN du certificat. </td> 
  </tr> 
 </tbody> 
</table>

1. Enregistrez le fichier en cliquant avec le bouton droit **[!UICONTROL (modified)]** sur la partie supérieure de la fenêtre et en cliquant sur **[!UICONTROL Save]**. [!DNL Insight] tentera de se connecter au serveur de répéteurs en utilisant les paramètres que vous avez spécifiés. Si une connexion est établie, une icône de serveur verte s&#39;affiche dans l&#39; [!DNL Servers Manager] interface. Si une connexion ne peut pas être établie, une icône rouge apparaît.

   For more information about the [!DNL Servers Manager] interface, see the * [!DNL Insight] User Guide*.

