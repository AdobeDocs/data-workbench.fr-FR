---
description: Le Gestionnaire de fichiers de serveur permet d’administrer et de gérer à distance les ordinateurs de serveur de Data Workbench à partir de n’importe quel Data Workbench autorisé en fournissant l’accès à tous les répertoires et fichiers du répertoire d’installation du produit, y compris les fichiers de configuration et de recherche.
title: Gestionnaire des fichiers de serveur
uuid: 62625b9d-587f-4a78-8328-2270869909f8
exl-id: 9ac7e95d-47e5-4862-a16e-bee0df1d3d15
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 2%

---

# Gestionnaire des fichiers de serveur{#server-files-manager}

{{eol}}

Le Gestionnaire de fichiers de serveur permet d’administrer et de gérer à distance les ordinateurs de serveur de Data Workbench à partir de n’importe quel Data Workbench autorisé en fournissant l’accès à tous les répertoires et fichiers du répertoire d’installation du produit, y compris les fichiers de configuration et de recherche.

Vous pouvez accéder au [!DNL Server Files Manager] en utilisant la variable [!DNL Admin] ainsi qu’en cliquant avec le bouton droit sur le noeud de l’ordinateur du serveur de Data Workbench dans la [!DNL Servers Manager] et clic **[!UICONTROL Server Files]**.

![](assets/vis_FileManager.png)

>[!NOTE]
>
>Vous pouvez créer de nouveaux gestionnaires de fichiers serveur qui affichent les répertoires sélectionnés. Voir [Création de nouveaux gestionnaires de fichiers serveur](../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-svr-files-mgrs.md#concept-6e8f63273109443699a8f61b1a2ea816).

La colonne de gauche de [!DNL Server Files Manager] répertorie les noms des fichiers et des dossiers. Les coches dans les colonnes centrale et droite indiquent où résident ces répertoires et fichiers dans la structure de fichiers.

Si un fichier réside dans le répertoire d’installation du produit, la variable *nom du serveur* (par exemple, serveur de Data Workbench) contient une coche. Si un fichier réside sur l’ordinateur de l’utilisateur Data Workbench dans la variable *Répertoire d’installation de Data Workbench*\Temp, le répertoire [!DNL Temp] contient une coche. La couleur des coches indique si les fichiers situés à différents emplacements ont été modifiés en même temps.

* Une coche rouge dans la colonne nom du serveur indique que le dossier ou le fichier réside sur l’ordinateur du serveur Data Workbench.
* Coche rouge dans la variable [!DNL Temp] indique que la copie locale du fichier ou du dossier a la même date et heure de modification que le fichier ou le dossier sur l’ordinateur du serveur de Data Workbench.
* Coche blanche dans la variable [!DNL Temp] indique que le fichier ou le dossier dans la variable *Répertoire d’installation de Data Workbench*\Temp a une date et une heure de modification différentes de celles du fichier ou du dossier sur l’ordinateur du serveur de Data Workbench.

Le graphique suivant illustre la variable [!DNL Server Files Manager] avec des coches rouges et blanches :

![](assets/vis_FileManager_RedWhiteChecks.png)

**Pour gérer les répertoires et les fichiers à l’aide de la méthode[!DNL Server Files Manager]**

Vous pouvez utiliser la variable [!DNL Server Files Manager] pour manipuler les répertoires et les fichiers sur un ordinateur de serveur de Data Workbench.

Le tableau suivant répertorie les tâches qui peuvent être effectuées à l’aide de la variable [!DNL Server Files Manager]:

<table id="table_D217AE5A878542EC8B604812A61819C3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour effectuer cette tâche.. </th> 
   <th colname="col2" class="entry"> Procédez comme suit : </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pour afficher les fichiers dans n’importe quel répertoire </p> </td> 
   <td colname="col2"> <p>Cliquez sur le nom du répertoire pour en visualiser le contenu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour masquer le contenu d’un répertoire </p> </td> 
   <td colname="col2"> <p>Cliquez sur le nom du répertoire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour afficher les détails d’un répertoire </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit sur la cellule en regard du répertoire dans le nom du serveur ou <span class="wintitle"> Temp</span> colonne . Les informations suivantes s’affichent : </p> 
    <ul id="ul_2DA5C8D0E95F4BCC8F7E25D05F00EB02"> 
     <li id="li_3FDECC14D62543B183C3509C338DF432">Chemin d’accès. Chemin d’accès du répertoire. </li> 
     <li id="li_9CF3989FD9E2427995F070E043FAD02C">Dir. Nom du répertoire. </li> 
     <li id="li_68AAA11907404D0BBF407ECD7CA2E467">De. Emplacement du répertoire, distant ou temporaire. </li> 
     <li id="li_CB4AEEC89E424868B758465EC0B701B5">Date (colonne Temp uniquement). Date de création ou date de la dernière révision de la copie locale. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour afficher les détails d’un fichier </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche en regard du fichier dans le nom du serveur ou <span class="wintitle"> Temp</span> colonne . Les informations suivantes s’affichent : </p> <p> 
     <ul id="ul_C4E6CB86D1774D739B5ECF48AF8DB628"> 
      <li id="li_7A6D39CF8C064FDDAB87F8D4E50FA832">Chemin d’accès. Chemin d’accès au fichier  </li> 
      <li id="li_9C735B6F0A2541F1992B845359C3685A">Fichier. Le nom du fichier. </li> 
      <li id="li_3EB903E4F4C44A6093732C588F0125EF">De. Emplacement du répertoire, distant ou temporaire. </li> 
      <li id="li_C1FED4F98F854D5892DBAD9F9E1D47B8">Date. Date de la dernière révision du fichier. </li> 
      <li id="li_7477C727C62F4406BB2026063E41F2AE">Taille. Taille du fichier. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour télécharger un répertoire sur votre ordinateur local </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche dans la <i>nom du serveur</i> pour ce répertoire et cliquez sur <span class="uicontrol"> Rendre le répertoire local</span>. Une coche pour le répertoire apparaît dans la <span class="wintitle"> Temp</span> colonne . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour télécharger un fichier sur votre ordinateur local </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche dans la <i>nom du serveur</i> pour ce fichier, puis cliquez sur <span class="uicontrol"> Rendre local</span>. Une coche pour le fichier apparaît dans la variable <span class="wintitle"> Temp</span> colonne . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour télécharger la dernière partie d’un fichier journal sur votre ordinateur local </p> </td> 
   <td colname="col2"> <p>Pour éviter d’avoir à télécharger l’intégralité d’un fichier journal (notamment lorsque vous savez que le message d’erreur se trouve à la fin du fichier), cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom du serveur pour le fichier, puis cliquez sur . <span class="uicontrol"> Fin</span>, puis sélectionnez la taille de la partie à télécharger. Une coche pour le fichier apparaît dans la variable <span class="wintitle"> Temp</span> colonne . Le fichier local contient uniquement la quantité de données que vous avez spécifiée, à partir de la fin du fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour ouvrir un répertoire </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche du répertoire dans la fonction <span class="wintitle"> Temp</span> et cliquez sur <span class="uicontrol"> Ouvrir</span> &gt; <span class="uicontrol"> folder</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pour ouvrir un fichier </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche du fichier dans la <span class="wintitle"> Temp</span> colonne, cliquez sur <span class="uicontrol"> Ouvrir</span>, puis cliquez sur <span class="uicontrol"> Data Workbench</span>, <span class="uicontrol"> dans Notepad</span>ou <span class="uicontrol"> folder</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enregistrement d’une copie locale d’un répertoire sur le serveur Data Workbench </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche du répertoire dans la fonction <span class="wintitle"> Temp</span> et cliquez sur <span class="uicontrol"> Enregistrer le répertoire dans</span> &gt; <i>&lt;<span class="uicontrol"> nom du profil</span>&gt;</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enregistrer une copie locale d’un fichier sur le serveur Data Workbench </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche du fichier dans la <span class="wintitle"> Temp</span> et cliquez sur <span class="uicontrol"> Enregistrer dans</span> &gt; <i>&lt;<span class="uicontrol"> nom du profil</span>&gt;</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Suppression d’une copie locale d’un répertoire ou d’un fichier </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche du répertoire ou du fichier dans le <span class="wintitle"> Temp</span> et cliquez sur <span class="uicontrol"> Supprimer</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Copier et coller un fichier en tant que pièce jointe à un email dans Microsoft Outlook </p> </td> 
   <td colname="col2"> <p>Cliquez avec le bouton droit de la souris sur la coche du fichier dans la <span class="wintitle"> Temp</span> et cliquez sur <span class="uicontrol"> Copier</span>. Dans le corps de votre email, appuyez sur Ctrl+v pour joindre le fichier. </p> </td> 
  </tr> 
 </tbody> 
</table>
