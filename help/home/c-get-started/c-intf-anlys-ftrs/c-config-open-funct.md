---
description: La fonctionnalité d’ouverture vous permet d’ouvrir des éléments tels que des documents ou des URI dans des applications externes telles qu’un éditeur de texte ou un navigateur Web.
solution: Analytics
title: Configuration de la fonctionnalité d’ouverture
topic: Data workbench
uuid: dfa79a2b-e9ff-4e62-b15b-ae7911adeafd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration de la fonctionnalité d’ouverture{#configure-open-functionality}

La fonctionnalité d’ouverture vous permet d’ouvrir des éléments tels que des documents ou des URI dans des applications externes telles qu’un éditeur de texte ou un navigateur Web.

La fonctionnalité d’ouverture est actuellement configurée uniquement dans l’ [!DNL Site] application et uniquement pour l’ouverture d’URI. Cette section fournit des informations sur la configuration de la fonctionnalité Open URI pour [!DNL Site]. Pour plus d’informations sur la configuration de la fonctionnalité Ouvrir pour une autre application ou pour ouvrir d’autres éléments, contactez les services de conseil Adobe.

Dans [!DNL Site]ce cas, vous pouvez cliquer avec le bouton droit de la souris sur un URI à partir d’un recouvrement de page ou d’un tableau pour afficher l’URI dans l’application pour laquelle il a été formaté. Par exemple, à partir d’une visualisation de tableau URI, vous pouvez cliquer sur un URI pour afficher une page Web dans un navigateur Web.

Pour ouvrir un URI à partir d’une visualisation, vous devez d’abord modifier le [!DNL Open URI.cfg] fichier pour la dimension URI afin d’identifier les conventions d’emplacement et d’appellation utilisées par les outils de données pour ouvrir l’URI. Pour afficher un URI dans son format natif (HTML, par exemple), les outils de données doivent avoir accès à l’emplacement référencé et à l’application nécessaire pour ouvrir cet élément. Par exemple, pour afficher une page Web, les outils de données doivent avoir accès à Internet et avoir un navigateur Web installé.

**Pour modifier Open URI.vw**

1. In the [!DNL Profile Manager], click **[!UICONTROL Context]** > **[!UICONTROL Dimension Element]** > **[!UICONTROL URI]**.
1. Dans le dossier URI, cliquez avec le bouton droit de la souris sur la coche en regard du [!DNL Open URI.vw]fichier et cliquez sur **[!UICONTROL Make Local]**. Une coche pour ce fichier apparaît dans la [!DNL User] colonne.
1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée, puis cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Insight]** si le fichier est un [!DNL .cfg] fichier ou **[!UICONTROL Open]** > **[!UICONTROL in Notepad]** s’il s’agit d’un [!DNL .vw] fichier.
1. Cliquez sur **[!UICONTROL Command]**, puis **[!UICONTROL Parameters]** pour afficher le contenu du fichier.
1. Modifiez le [!DNL Site] paramètre et le paramètre Modèle si nécessaire :

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
   <td colname="col2"> <p>Emplacement des URI que vous souhaitez ouvrir. </p> <p>Exemple : monsite.com </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modèle </p> </td> 
   <td colname="col2"> <p>Paramètres que les outils de données doivent utiliser pour localiser et ouvrir les URI. </p> <p>Exemple : <span class="filepath"> http://%Site%%URI%</span> </p> <p>Le modèle par défaut illustré dans l’exemple indique aux Outils de données d’ouvrir un navigateur Web, de rechercher l’emplacement défini dans le paramètre <span class="wintitle"> Site</span> , puis de localiser l’élément de dimension URI que vous essayez d’ouvrir. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Enregistrez le fichier.
1. Pour mettre cette modification à la disposition de tous les utilisateurs du profil de travail, cliquez avec le bouton droit de la souris sur la coche du [!DNL .vw] fichier dans la [!DNL User] colonne et cliquez sur **[!UICONTROL Save to]** > **[!UICONTROL working profile name]**.

