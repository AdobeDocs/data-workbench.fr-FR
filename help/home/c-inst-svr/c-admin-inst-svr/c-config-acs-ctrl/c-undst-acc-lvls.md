---
description: Les niveaux d’accès décrivent les URI de l’ordinateur qu’un groupe d’utilisateurs est autorisé à lire ou à modifier.
solution: Insight
title: Présentation des niveaux d'accès
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Présentation des niveaux d&#39;accès{#understanding-access-levels}

Les niveaux d’accès décrivent les URI de l’ordinateur qu’un groupe d’utilisateurs est autorisé à lire ou à modifier.

Suivez ces directives pour définir les niveaux d’accès souhaités par les utilisateurs de votre entreprise :

* Des URI spécifiques sans barre oblique de fin limitent uniquement l’accès à cet URI. Par exemple, [!DNL /Components/Communications.cfg] permet d’accéder au [!DNL Communications.cfg]fichier uniquement.

* Une barre oblique (/) à la fin, spécifiant un répertoire, permet aux membres du groupe d’accéder à toute URI commençant par cette chaîne. Par exemple, /Profils/ permet d’accéder à l’intégralité du répertoire Profils.
* Un symbole de symbole dollar ($) à la fin limite l’accès à l’URI exact uniquement, même s’il s’agit d’un répertoire. Par exemple, /Profils/$ permet de lire le répertoire principal Profils, mais pas les fichiers qu’il contient.

   Pour accéder à des fichiers spécifiques, vous n&#39;avez pas besoin d&#39;utiliser un $ à la fin.

   Par exemple, [!DNL /Components/Communications.cfg] et [!DNL /Components/Communications.cfg$] fournissent le même accès.

* Un symbole de pourcentage (%) peut être utilisé avec CN (Nom commun) pour autoriser l’accès. Par exemple, /Users/%CN%/ permet d’accéder au répertoire Utilisateur correspondant au nom commun du certificat SSL de l’ [!DNL Insight] utilisateur. Notez que cette syntaxe ne peut être utilisée qu’une seule fois dans un URI.

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
   <td colname="col4"> <p>Accès en lecture et en écriture à tous les répertoires <span class="keyword"> Insight Server</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Capteurs </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>Accès en lecture et en écriture aux deux fichiers que les <span class="wintitle"> capteurs</span> utilisent pour communiquer avec le serveur <span class="keyword"></span>d’informations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilisateurs </p> </td> 
   <td colname="col2"> <p>/Profils/ </p> <p>/État/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Utilisateurs/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>Accès en lecture et en écriture au répertoire utilisateur correspondant au nom commun du certificat SSL de l’utilisateur <span class="keyword"> Insight</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilisateurs puissants </p> </td> 
   <td colname="col2"> <p>/Profils/$ </p> <p>/État/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Utilisateurs/$ </p> </td> 
   <td colname="col3"> <p>/Profils/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>Les utilisateurs disposant des droits d’accès sont autorisés à accéder aux mêmes utilisateurs que les utilisateurs, avec la possibilité d’écrire dans le répertoire Profils. Ces utilisateurs peuvent modifier les profils et activer la mise à jour automatique des modifications pour d’autres utilisateurs d’ <span class="keyword"> Insight</span> , comme lors de la distribution des espaces de travail nouvellement définis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveurs de cluster </p> </td> 
   <td colname="col2"> <p>/Composants pour les serveurs de traitement/ </p> <p>/Addresses/ </p> <p>/Profils/ </p> <p>/Lookups/ </p> <p>/Access Control/ </p> <p>/Bin/ </p> <p>/Journaux/ </p> </td> 
   <td colname="col3"> <p>/Cluster/ </p> </td> 
   <td colname="col4"> <p>Accès en lecture et en écriture au répertoire de la grappe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveurs de rapports </p> </td> 
   <td colname="col2"> <p>/Profils/$ </p> <p>/État/ </p> <p>/Software/ </p> <p>/Addresses/ </p> <p>/Utilisateurs/$ </p> </td> 
   <td colname="col3"> <p>/Profils/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>Les ordinateurs de rapports peuvent accéder aux mêmes utilisateurs que les utilisateurs Power, avec la possibilité supplémentaire d’écrire dans le fichier <span class="filepath"> ReportStatus.vsp</span> . </p> </td> 
  </tr> 
 </tbody> 
</table>

**Pour configurer le contrôle d&#39;accès**

Lors de la définition de groupes de contrôle d’accès, vous devez inclure tous les administrateurs système, utilisateurs, serveurs de cluster et utilisateurs de serveurs de rapports qui doivent accéder à cet [!DNL Insight Server] ordinateur. Vous pouvez autoriser l’accès à l’aide de l’adresse IP ou des informations de certificat SSL, telles que le nom commun ou l’organisation.

>[!NOTE]
>
>Lorsque le [!DNL Access Control.cfg] fichier est modifié [!DNL Insight Server], toutes les connexions existantes sont arrêtées et sont forcées de se reconnecter. Les connexions sont comparées aux autorisations du [!DNL Access Control.cfg] fichier mis à jour. Dans l’interface du Gestionnaire de serveurs, l’ [!DNL Insight Server] icône devient temporairement rouge, puis verte à nouveau, car la connexion est arrêtée et forcée de se reconnecter avec toutes les autres.

1. Dans l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs.

1. Cliquez avec le bouton droit de la souris sur l’icône du [!DNL Insight Server] fichier à configurer, puis cliquez sur **[!UICONTROL Files]**.

1. Dans la [!DNL Server Files Manager], cliquez **[!UICONTROL Access Control]** pour en afficher le contenu. Le [!DNL Access Control.cfg] fichier se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom *du* serveur [!DNL Access Control.cfg] et cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Access Control.cfg].

1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la [!DNL Temp] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. Dans la [!DNL Access Control.cfg] fenêtre, cliquez **[!UICONTROL Access Control Groups]** pour en afficher le contenu.

   ![](assets/access_ctrl_cfg.png)

1. Pour ajouter un nouveau groupe de contrôle d’accès :

   1. Cliquez avec le bouton droit de la souris **[!UICONTROL Access Control Groups]** , puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

   1. Cliquez avec le bouton droit de la souris **[!UICONTROL Members]** , puis cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

      Les membres des groupes par défaut ne sont pas prédéfinis. Par défaut, l’accès administrateur est accordé à 127.0.0.1 (hôte local) et [!DNL Sensor] l’accès est accordé à l’adresse IP :*. Tous les autres membres du groupe de contrôle d&#39;accès doivent être définis.

   1. Renseignez les paramètres.

1. Pour ajouter de nouveaux membres à un groupe de contrôle d’accès existant :

   1. Cliquez avec le bouton droit **[!UICONTROL Members]** sous le groupe de contrôle d’accès approprié et cliquez sur **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Enregistrez le fichier en cliquant avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre, puis en cliquant **[!UICONTROL Save]**.

1. Pour enregistrer les modifications apportées localement à la [!DNL Insight Server] machine, dans la [!DNL Server Files Manager]colonne, cliquez avec le bouton droit de la souris sur la coche [!DNL Access Control.cfg] dans la [!DNL Temp] colonne, puis cliquez sur **[!UICONTROL Save to]** &lt; ***[!UICONTROL server name]**>.*

