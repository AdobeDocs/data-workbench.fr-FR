---
description: La fonctionnalité d’ouverture vous permet d’ouvrir des éléments tels que des documents ou des URI dans des applications externes telles qu’un éditeur de texte ou un navigateur web.
title: Configurer la fonctionnalité ouverte
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
exl-id: c807a284-b544-41cf-958b-27b47d2142ce
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 2%

---

# Configurer la fonctionnalité ouverte{#configure-open-functionality}

{{eol}}

La fonctionnalité d’ouverture vous permet d’ouvrir des éléments tels que des documents ou des URI dans des applications externes telles qu’un éditeur de texte ou un navigateur web.

La fonctionnalité d’ouverture est actuellement configurée uniquement dans le [!DNL Site] et uniquement pour l’ouverture d’URI. Cette section fournit des informations sur la configuration de la fonctionnalité Open URI pour [!DNL Site]. Pour plus d’informations sur la configuration de la fonctionnalité Ouvrir pour une autre application ou pour ouvrir d’autres éléments, contactez les services de conseil d’Adobe.

Dans [!DNL Site], vous pouvez cliquer avec le bouton droit de la souris sur un URI d’une superposition ou d’un tableau de page pour afficher l’URI dans l’application pour laquelle il a été formaté. Par exemple, dans une visualisation de tableau URI, vous pouvez cliquer sur un URI pour afficher une page web dans un navigateur web.

Pour ouvrir une URI à partir d’une visualisation, vous devez d’abord modifier la variable [!DNL Open URI.cfg] pour la dimension URI afin d’identifier l’emplacement et les conventions d’affectation de noms que Data Workbench utilise pour ouvrir l’URI. Pour afficher un URI dans son format natif (par exemple, HTML), Data Workbench doit avoir accès à l’emplacement référencé et à l’application nécessaire pour ouvrir cet élément. Par exemple, pour afficher une page web, le Data Workbench doit avoir accès à Internet et disposer d’un navigateur web.

**Pour modifier Open URI.vw**

1. Dans le [!DNL Profile Manager], cliquez sur **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. Dans le dossier URI, cliquez avec le bouton droit de la souris sur la coche située en regard de l’objet [!DNL Open URI.vw]et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la variable [!DNL User] colonne .
1. Cliquez avec le bouton droit de la souris sur la coche que vous venez de créer, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]** si le fichier est un [!DNL .cfg] fichier ou **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** s’il s’agit d’une [!DNL .vw] fichier .
1. Cliquez sur **[!UICONTROL Command]**, puis **[!UICONTROL Parameters]** pour afficher le contenu du fichier.
1. Modifiez le [!DNL Site] et le paramètre Modèle selon les besoins :

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
   <td colname="col2"> <p>Paramètres que Data Workbench doit utiliser pour localiser et ouvrir les URI. </p> <p>Exemple : <span class="filepath"> https://%Site%%URI%</span> </p> <p>Le modèle par défaut illustré dans l’exemple indique au Data Workbench d’ouvrir un navigateur web, recherchez l’emplacement défini dans la variable <span class="wintitle"> Site</span> , puis recherchez l’élément de dimension URI que vous tentez d’ouvrir. </p> </td>
  </tr>
 </tbody>
</table>

1. Enregistrez le fichier.
1. Pour mettre cette modification à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche de la fonction [!DNL .vw] dans le fichier [!DNL User] et cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.
