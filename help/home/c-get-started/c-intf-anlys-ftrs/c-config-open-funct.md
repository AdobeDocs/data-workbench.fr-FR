---
description: La fonctionnalité d’ouverture vous permet d’ouvrir des éléments tels que des documents ou des URI dans des applications externes telles qu’un éditeur de texte ou un navigateur web.
title: Configurer la fonctionnalité ouverte
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
exl-id: c807a284-b544-41cf-958b-27b47d2142ce
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 2%

---

# Configurer la fonctionnalité ouverte{#configure-open-functionality}

La fonctionnalité d’ouverture vous permet d’ouvrir des éléments tels que des documents ou des URI dans des applications externes telles qu’un éditeur de texte ou un navigateur web.

La fonctionnalité d’ouverture est actuellement configurée uniquement dans l’application [!DNL Site] et uniquement pour l’ouverture d’URI. Cette section fournit des informations sur la configuration de la fonctionnalité Open URI pour [!DNL Site]. Pour plus d’informations sur la configuration de la fonctionnalité Ouvrir pour une autre application ou pour ouvrir d’autres éléments, contactez les services de conseil d’Adobe.

Dans [!DNL Site], vous pouvez cliquer avec le bouton droit de la souris sur un URI à partir d’une superposition ou d’un tableau de page pour afficher l’URI dans l’application pour laquelle il a été formaté. Par exemple, dans une visualisation de tableau URI, vous pouvez cliquer sur un URI pour afficher une page web dans un navigateur web.

Pour ouvrir un URI à partir d’une visualisation, vous devez d’abord modifier le fichier [!DNL Open URI.cfg] correspondant à la dimension URI afin d’identifier l’emplacement et les conventions d’affectation de nom utilisées par Data Workbench pour ouvrir l’URI. Pour afficher un URI dans son format natif (par exemple, HTML), Data Workbench doit avoir accès à l’emplacement référencé et à l’application nécessaire pour ouvrir cet élément. Par exemple, pour afficher une page web, le Data Workbench doit avoir accès à Internet et disposer d’un navigateur web.

**Pour modifier Open URI.vw**

1. Dans la balise [!DNL Profile Manager], cliquez sur **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. Dans le dossier URI, cliquez avec le bouton droit de la souris sur la coche en regard du fichier [!DNL Open URI.vw]et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la colonne [!DNL User].
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]** si le fichier est un fichier [!DNL .cfg] ou **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** s’il s’agit d’un fichier [!DNL .vw].
1. Cliquez sur **[!UICONTROL Command]**, puis sur **[!UICONTROL Parameters]** pour afficher le contenu du fichier.
1. Modifiez le paramètre [!DNL Site] et le paramètre Modèle selon les besoins :

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
   <td colname="col2"> <p>Paramètres que Data Workbench doit utiliser pour localiser et ouvrir les URI. </p> <p>Exemple : <span class="filepath"> https://%Site%%URI%</span> </p> <p>Le modèle par défaut illustré dans l’exemple indique au Data Workbench d’ouvrir un navigateur web, de rechercher l’emplacement défini dans le paramètre <span class="wintitle"> Site</span>, puis de localiser l’élément de dimension URI que vous tentez d’ouvrir. </p> </td>
  </tr>
 </tbody>
</table>

1. Enregistrez le fichier.
1. Pour mettre cette modification à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche du fichier [!DNL .vw] dans la colonne [!DNL User] et cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.
