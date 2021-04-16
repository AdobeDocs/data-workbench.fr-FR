---
description: La fonctionnalité d’ouverture vous permet d’ouvrir des éléments tels que des documents ou des URI dans des applications externes telles qu’un éditeur de texte ou un navigateur Web.
title: Configurer la fonctionnalité ouverte
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
exl-id: c807a284-b544-41cf-958b-27b47d2142ce
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 2%

---

# Configurer la fonctionnalité ouverte{#configure-open-functionality}

La fonctionnalité d’ouverture vous permet d’ouvrir des éléments tels que des documents ou des URI dans des applications externes telles qu’un éditeur de texte ou un navigateur Web.

La fonctionnalité d&#39;ouverture est actuellement configurée uniquement dans l&#39;application [!DNL Site] et uniquement pour les URI d&#39;ouverture. Cette section fournit des informations sur la configuration de la fonctionnalité Open URI pour [!DNL Site]. Pour plus d&#39;informations sur la configuration de la fonctionnalité Ouvrir pour une autre application ou pour ouvrir d&#39;autres éléments, contactez les services de conseil en Adobe.

Dans [!DNL Site], vous pouvez cliquer avec le bouton droit de la souris sur un URI à partir d’une incrustation de page ou d’un tableau pour afficher l’URI dans l’application pour laquelle il a été formaté. Par exemple, à partir d’une visualisation de tableau URI, vous pouvez cliquer sur un URI pour afficher une page Web dans un navigateur Web.

Pour ouvrir un URI à partir d’une visualisation, vous devez d’abord modifier le fichier [!DNL Open URI.cfg] pour la dimension URI afin d’identifier l’emplacement et les conventions d’attribution de noms que le Data Workbench utilise pour ouvrir l’URI. Pour vue d’un URI dans son format natif (HTML, par exemple), le Data Workbench doit avoir accès à l’emplacement référencé et à l’application nécessaire pour ouvrir cet élément. Par exemple, pour vue d’une page Web, le Data Workbench doit avoir accès à Internet et disposer d’un navigateur Web.

**Pour modifier Open URI.vw**

1. Dans le [!DNL Profile Manager], cliquez sur **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. Dans le dossier URI, cliquez avec le bouton droit de la souris sur la coche en regard du fichier [!DNL Open URI.vw]et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].
1. Cliquez avec le bouton droit sur la coche nouvellement créée et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]** si le fichier est un fichier [!DNL .cfg] ou **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** s&#39;il s&#39;agit d&#39;un fichier [!DNL .vw].
1. Cliquez sur **[!UICONTROL Command]**, puis sur **[!UICONTROL Parameters]** pour vue le contenu du fichier.
1. Modifiez le paramètre [!DNL Site] et le paramètre Template si nécessaire :

<table id="table_CDB316DB271F476AB9F9B557B86AFD25"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour ce paramètre... </th> 
   <th colname="col2" class="entry"> Fournissez ces informations... </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Site </p> </td> 
   <td colname="col2"> <p>Emplacement des URI que vous souhaitez ouvrir. </p> <p>Exemple : mysite.com </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modèle </p> </td> 
   <td colname="col2"> <p>Paramètres que le Data Workbench doit utiliser pour localiser et ouvrir les URI. </p> <p>Exemple : <span class="filepath"> http://%Site%%URI%</span> </p> <p>Le modèle par défaut illustré dans l’exemple indique au Data Workbench d’ouvrir un navigateur Web, de rechercher l’emplacement défini dans le paramètre <span class="wintitle"> Site</span>, puis de localiser l’élément de dimension URI que vous tentez d’ouvrir. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Enregistrez le fichier.
1. Pour mettre cette modification à la disposition de tous les utilisateurs du profil de travail, cochez la case du fichier [!DNL .vw] dans la colonne [!DNL User] et cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.
