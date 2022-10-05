---
description: Les niveaux d’accès décrivent les URI de la machine qu’un groupe d’utilisateurs est autorisé à lire ou à modifier.
title: Compréhension des niveaux d’accès
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
exl-id: 64e2dc39-1ca1-425b-bec7-acb10a8819c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 3%

---

# Compréhension des niveaux d’accès{#understanding-access-levels}

{{eol}}

Les niveaux d’accès décrivent les URI de la machine qu’un groupe d’utilisateurs est autorisé à lire ou à modifier.

Suivez ces instructions pour définir les niveaux d’accès souhaités par les utilisateurs de votre entreprise :

* Les URI spécifiques sans barre oblique restreignent l’accès à cet URI uniquement. Par exemple : [!DNL /Components/Communications.cfg] permet d’accéder au [!DNL Communications.cfg]fichier uniquement.

* Une barre oblique (/), spécifiant un répertoire, permet aux membres du groupe d’accéder à n’importe quel URI commençant par cette chaîne. Par exemple, /Profiles/ permet d’accéder à l’intégralité du répertoire Profils .
* Un symbole représentant un signe dollar ($) limite l’accès à l’URI exact uniquement, même s’il s’agit d’un répertoire. Par exemple, /Profiles/$ permet de lire le répertoire principal des profils, mais pas de lire les fichiers de ce répertoire.

   Pour accéder à des fichiers spécifiques, vous n’avez pas besoin d’utiliser un $ de fin.

   Par exemple : [!DNL /Components/Communications.cfg] et [!DNL /Components/Communications.cfg$] fournissent le même accès.

* Un symbole de pourcentage (%) peut être utilisé avec CN (nom commun) pour autoriser l’accès. Par exemple, /Users/%CN%/ permet d’accéder au répertoire des utilisateurs correspondant au nom commun de certificat SSL de la variable [!DNL Insight] utilisateur. Notez que cette syntaxe ne peut être utilisée qu’une seule fois dans un URI.

Les URI des groupes de contrôle d’accès prédéfinis ont été configurés comme suit :

<table id="table_8E6FDD741BF24E2DAD96A2919FAE6C7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom de groupe </th> 
   <th colname="col2" class="entry"> Accès en lecture seule </th> 
   <th colname="col3" class="entry"> Accès en lecture-écriture </th> 
   <th colname="col4" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Administrateurs </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/ </p> </td> 
   <td colname="col4"> <p>Accès en lecture et en écriture à tous les <span class="keyword"> Serveur Insight</span> répertoires. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Capteurs </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>Accès en lecture et en écriture aux deux fichiers que la variable <span class="wintitle"> Capteurs</span> utilisez pour communiquer avec le <span class="keyword"> Serveur Insight</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilisateurs </p> </td> 
   <td colname="col2"> <p>/Profils/ </p> <p>/État/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Utilisateurs/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>Accès en lecture et en écriture au répertoire utilisateur correspondant au nom commun du certificat SSL de la variable <span class="keyword"> Insight</span> utilisateur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilisateurs experts </p> </td> 
   <td colname="col2"> <p>/Profils/$ </p> <p>/État/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Utilisateurs/$ </p> </td> 
   <td colname="col3"> <p>/Profils/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>Les utilisateurs expérimentés ont le même accès que les utilisateurs, avec la possibilité d’écrire dans le répertoire Profils . Ces utilisateurs peuvent modifier les profils et permettre la mise à jour automatique des modifications pour d’autres <span class="keyword"> Insight</span> lors de la distribution d’espaces de travail nouvellement définis, par exemple. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveurs de grappe </p> </td> 
   <td colname="col2"> <p>/Components pour les serveurs de traitement/ </p> <p>/Addresses/ </p> <p>/Profils/ </p> <p>/Lookups/ </p> <p>/Contrôle d’accès/ </p> <p>/Bin/ </p> <p>/Journaux/ </p> </td> 
   <td colname="col3"> <p>/Cluster/ </p> </td> 
   <td colname="col4"> <p>Accès en lecture et en écriture au répertoire de la grappe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveurs de rapports </p> </td> 
   <td colname="col2"> <p>/Profils/$ </p> <p>/État/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Utilisateurs/$ </p> </td> 
   <td colname="col3"> <p>/Profils/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>Les machines de rapports ont le même accès que les utilisateurs Power, avec la possibilité d’écrire dans le <span class="filepath"> ReportStatus.vsp</span> fichier . </p> </td> 
  </tr> 
 </tbody> 
</table>

**Pour configurer le contrôle d’accès**

Lors de la définition des groupes de contrôle d’accès, vous devez inclure tous les administrateurs système, utilisateurs, serveurs de cluster et utilisateurs du serveur de rapports ayant besoin d’un accès à ces groupes. [!DNL Insight Server] ordinateur. Vous pouvez accorder l’accès à l’aide de l’adresse IP ou des informations de certificat SSL, telles que le nom commun ou l’organisation.

>[!NOTE]
>
>Lorsque la variable [!DNL Access Control.cfg] est modifié lors de la [!DNL Insight Server], toutes les connexions existantes sont arrêtées et forcées de se reconnecter. Les connexions sont comparées aux autorisations dans la mise à jour [!DNL Access Control.cfg] fichier . Dans l’interface du Gestionnaire de serveurs, la variable [!DNL Insight Server] L’icône devient temporairement rouge, puis verte à nouveau, car la connexion est arrêtée et forcée de se reconnecter avec tous les autres.

1. Sur le [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs .

1. Cliquez avec le bouton droit de la souris sur l’icône du [!DNL Insight Server] vous souhaitez configurer et cliquer sur **[!UICONTROL Files]**.

1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Access Control]** pour afficher son contenu. Le [!DNL Access Control.cfg] se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la *nom du serveur* column pour [!DNL Access Control.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la variable [!DNL Temp] column pour [!DNL Access Control.cfg].

1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans le [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. Dans le [!DNL Access Control.cfg] fenêtre, cliquez sur **[!UICONTROL Access Control Groups]** pour afficher son contenu.

   ![](assets/access_ctrl_cfg.png)

1. Pour ajouter une nouvelle population témoin d’accès :

   1. Clic droit **[!UICONTROL Access Control Groups]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

   1. Clic droit **[!UICONTROL Members]** et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

      Les membres des groupes par défaut ne sont pas prédéfinis. Par défaut, l’accès administrateur est accordé à 127.0.0.1 (hôte local) et [!DNL Sensor] l’accès est accordé à l’adresse IP :&#42;. Tous les autres membres de la population témoin d’accès doivent être définis.

   1. Renseignez les paramètres.

1. Pour ajouter de nouveaux membres à une population témoin d’accès existante :

   1. Clic droit **[!UICONTROL Members]** sous la population témoin d’accès appropriée, cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Enregistrez le fichier en cliquant avec le bouton droit de la souris **[!UICONTROL (modified)]** en haut de la fenêtre, puis en cliquant sur **[!UICONTROL Save]**.

1. Pour enregistrer les modifications apportées localement à la variable [!DNL Insight Server] , dans le [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche pour [!DNL Access Control.cfg] dans le [!DNL Temp] , puis cliquez sur **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]**>*.
