---
description: Le Gestionnaire de fichiers du serveur vous permet d’administrer et de gérer à distance les ordinateurs des serveurs Outils de données à partir de n’importe quel outil de données autorisé en donnant accès à tous les répertoires et fichiers du répertoire d’installation du produit, y compris les fichiers de configuration et de recherche.
solution: Analytics
title: Gestionnaire des fichiers serveur
topic: Data workbench
uuid: 62625b9d-587f-4a78-8328-2270869909f8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Gestionnaire des fichiers serveur{#server-files-manager}

Le Gestionnaire de fichiers du serveur vous permet d’administrer et de gérer à distance les ordinateurs des serveurs Outils de données à partir de n’importe quel outil de données autorisé en donnant accès à tous les répertoires et fichiers du répertoire d’installation du produit, y compris les fichiers de configuration et de recherche.

Vous pouvez accéder à l’ [!DNL Server Files Manager] application à l’aide du [!DNL Admin] menu ainsi qu’en cliquant avec le bouton droit sur le noeud de l’ordinateur du serveur Outils de données dans le [!DNL Servers Manager] menu et en cliquant sur **[!UICONTROL Server Files]**.

![](assets/vis_FileManager.png)

>[!NOTE]
>
>Vous pouvez créer de nouveaux gestionnaires de fichiers serveur qui affichent les répertoires sélectionnés. Voir [Création de gestionnaires](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816)de fichiers serveur.

La colonne de gauche de [!DNL Server Files Manager] répertorie les noms de fichier et de dossier. Les coches dans les colonnes centre et droit indiquent l’emplacement de ces répertoires et fichiers dans la structure de fichiers.

Si un fichier réside dans le répertoire d’installation du produit, la colonne du nom *du* serveur (serveur Outils de données, par exemple) contient une coche. Si un fichier réside sur l’ordinateur de l’utilisateur des outils de données dans le répertoire *d’installation des outils de* données\Temp, la [!DNL Temp] colonne contient une coche. La couleur des coches indique si les fichiers qui résident à différents emplacements ont été modifiés en même temps.

* Une coche rouge dans la colonne nom du serveur indique que le dossier ou le fichier réside sur l’ordinateur du serveur Outils de données.
* Une coche rouge dans la [!DNL Temp] colonne indique que la copie locale du fichier ou du dossier a la même date et heure de modification que le fichier ou le dossier sur l’ordinateur du serveur Outils de données.
* Une coche blanche dans la [!DNL Temp] colonne indique que le fichier ou le dossier du répertoire *d’installation des outils de* données\Temp a une date et une heure de modification différentes de celles du fichier ou du dossier sur l’ordinateur du serveur des outils de données.

Le graphique suivant présente les coches [!DNL Server Files Manager] en rouge et blanc :

![](assets/vis_FileManager_RedWhiteChecks.png)

**Pour gérer des répertoires et des fichiers à l’aide de la variable[!DNL Server Files Manager]**

Vous pouvez utiliser le [!DNL Server Files Manager] pour manipuler des répertoires et des fichiers sur un ordinateur serveur de Outils de données.

Le tableau suivant répertorie les tâches qui peuvent être exécutées à l’aide de la [!DNL Server Files Manager]:

<table id="table_D217AE5A878542EC8B604812A61819C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour effectuer cette tâche... </th> 
   <th colname="col2" class="entry"> Procédez comme suit : </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pour afficher les fichiers dans n’importe quel répertoire </p> </td> 
   <td colname="col2"> <p>Cliquez sur le nom du répertoire pour en afficher le contenu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour masquer le contenu d’un répertoire </p> </td> 
   <td colname="col2"> <p>Cliquez sur le nom du répertoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour afficher des détails sur un répertoire </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la cellule en regard du répertoire dans le nom du serveur ou dans la colonne <span class="wintitle"> Temp</span> . Les informations suivantes s’affichent : </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">Chemin d’accès. Chemin d’accès du répertoire. </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">Dir. Nom du répertoire. </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">De. Emplacement du répertoire, distant ou temporaire. </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">Date (colonne Temp uniquement). Date de création ou date de la dernière révision de la copie locale. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour afficher les détails d’un fichier </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche en regard du fichier dans le nom du serveur ou dans la colonne <span class="wintitle"> Temp</span> . Les informations suivantes s’affichent : </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">Chemin d’accès. Chemin d’accès du fichier. </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">Fichier. Nom du fichier. </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">De. Emplacement du répertoire, distant ou temporaire. </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">Date. Date de la dernière révision du fichier. </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">Taille. Taille du fichier. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour télécharger un répertoire sur votre ordinateur local </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom <i>du</i> serveur pour ce répertoire, puis cliquez sur <span class="uicontrol"> Rendre le répertoire local</span>. Une coche du répertoire s’affiche dans la colonne <span class="wintitle"> Temp</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour télécharger un fichier sur votre ordinateur local </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom <i>du</i> serveur pour ce fichier, puis cliquez sur <span class="uicontrol"> Rendre local</span>. Une coche du fichier apparaît dans la colonne <span class="wintitle"> Temp</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour télécharger la dernière partie d’un fichier journal sur votre ordinateur local </p> </td> 
   <td colname="col2"> <p>Pour éviter d’avoir à télécharger un fichier journal complet (surtout lorsque vous savez que le message d’erreur se trouve à la fin du fichier), cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom de serveur du fichier, cliquez sur <span class="uicontrol"> Queue</span>et sélectionnez la taille de la partie à télécharger. Une coche du fichier apparaît dans la colonne <span class="wintitle"> Temp</span> . Le fichier local contient uniquement la quantité de données que vous avez spécifiée, à partir de la fin du fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour ouvrir un répertoire </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche du répertoire dans la colonne <span class="wintitle"> Temp</span> et cliquez sur <span class="uicontrol"> Ouvrir</span> &gt; <span class="uicontrol"> dossier</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour ouvrir un fichier </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne <span class="wintitle"> Temp</span> , cliquez sur <span class="uicontrol"> Ouvrir</span>, puis sur dans les Outils <span class="uicontrol"></span><span class="uicontrol"> de données, dans le Bloc-notes ou dans le dossier.</span><span class="uicontrol"></span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enregistrement d’une copie locale d’un répertoire sur le serveur Outils de données </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche du répertoire dans la colonne <span class="wintitle"> Temp</span> et cliquez sur <span class="uicontrol"> Enregistrer le répertoire dans</span> &gt; <i>&lt;nom<span class="uicontrol"></span>du profil&gt;.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enregistrer une copie locale d’un fichier sur le serveur Outils de données </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne <span class="wintitle"> Temp</span> et cliquez sur <span class="uicontrol"> Enregistrer dans</span> &gt; <i>&lt;nom<span class="uicontrol"></span>du profil&gt;.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Suppression d’une copie locale d’un répertoire ou d’un fichier </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche du répertoire ou du fichier dans la colonne <span class="wintitle"> Temp</span> et cliquez sur <span class="uicontrol"> Supprimer</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Copier et coller un fichier en tant que pièce jointe d'un courrier électronique dans Microsoft Outlook </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne <span class="wintitle"> Temp</span> et cliquez sur <span class="uicontrol"> Copier</span>. Dans le corps de votre courrier électronique, appuyez sur Ctrl+v pour joindre le fichier. </p> </td> 
  </tr> 
 </tbody> 
</table>

