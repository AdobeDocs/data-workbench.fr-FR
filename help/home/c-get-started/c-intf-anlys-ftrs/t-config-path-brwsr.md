---
description: Les navigateurs de chemins peuvent être configurés pour fonctionner avec toute combinaison de dimension de base, de dimension de groupe, de dimension de niveau et de mesure qui convient à votre application et à votre jeu de données.
solution: Analytics
title: Configuration d’un navigateur de chemins d’accès
topic: Data workbench
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration d’un navigateur de chemins d’accès{#configure-a-path-browser}

Les navigateurs de chemins peuvent être configurés pour fonctionner avec toute combinaison de dimension de base, de dimension de groupe, de dimension de niveau et de mesure qui convient à votre application et à votre jeu de données.

Une fois que vous avez configuré un navigateur de chemins, il est répertorié avec d’autres navigateurs de chemins dans le [!DNL Add Visualization] menu.

1. Dans la [!DNL Profile Manager], cliquez sur **[!UICONTROL Menu]**, puis sur **[!UICONTROL Add Visualization]** et **[!UICONTROL Path Browser]**.

   Au moins un [!DNL *.vw] fichier réside dans le répertoire du navigateur de chemins d’accès.

1. Cliquez avec le bouton droit de la souris sur la coche du fichier souhaité, puis cliquez sur **[!UICONTROL Make Local]**.
1. Cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Modifiez les paramètres du fichier à l’aide de l’exemple de fichier et du tableau suivants comme guides :

   ```
   window = simpleBorderWindow: 
     client = pathBrowser: 
       Left Path = vector: 0 items
       Map = ref: wdata/model/dim/base dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       Map Level = ref: wdata/model/dim/level dimension name
       Metric = ref: wdata/model/metric/metric name
       Right Path = vector: 0 items
       size = v3d: (673, 279, 0)
     pos = v3d: (714, 143, 0)
     size = v3d: (673, 298, 0)
   ```

<table id="table_1DCCB4B24B554B72A781B304B5EB155E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour ce paramètre... </th> 
   <th colname="col2" class="entry"> Fournissez ces informations... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Nom de la dimension de base</i> </p> </td> 
   <td colname="col2"> <p>Nom de la dimension dont les éléments apparaissent dans le navigateur de chemins. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nom de la dimension du groupe</i> </p> </td> 
   <td colname="col2"> <p>Nom de la dimension qui détermine comment les éléments de la dimension de niveau sont regroupés pour former les chemins dans un navigateur de chemins. Plus précisément, les éléments de dimension de niveau associés à un chemin unique dans un navigateur de chemins ne peuvent pas couvrir plus d’un élément d’une dimension de groupe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nom de la dimension de niveau</i> </p> </td> 
   <td colname="col2"> <p>Nom du niveau (parent) de la dimension de base dont vous faites glisser les éléments vers le navigateur de chemins. Lorsque vous suivez un chemin d’un élément de dimension de base à un autre, vous passez d’un élément de dimension de niveau à un autre. Lorsque vous sélectionnez un chemin d’accès aux éléments de dimension de base, vous sélectionnez des données pour les éléments correspondants de la dimension de niveau. La sélection inclut toujours les éléments de la dimension de niveau qui se rapportent à la racine, et elle est affinée en ajoutant d’autres éléments au chemin. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nom de la mesure</i> </p> </td> 
   <td colname="col2"> <p>Nom de la mesure dont la valeur pour un élément donné est proportionnelle à l’épaisseur du chemin conduisant à cet élément. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Pour plus d’informations sur la dimension de base, la dimension de groupe, la dimension de niveau et la mesure pour un navigateur de chemins, voir Navigateurs de [chemins](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b).

1. Dans le Bloc-notes, cliquez sur **[!UICONTROL File]** > **[!UICONTROL Save As]** pour enregistrer le fichier sous un nouveau nom basé sur la dimension de groupe, c’est-à-dire le nom *de la dimension* Groupe.vw.

   Assurez-vous d’enregistrer le fichier dans le répertoire du navigateur de chemins d’accès.

   >[!NOTE]
   >
   >Pour vous assurer que votre navigateur de chemins d’accès est enregistré en tant que [!DNL *.vw] fichier, dans la [!DNL Save As] fenêtre, définissez Enregistrer en tant que type sur Tous les fichiers.

1. (Facultatif) Pour rendre les modifications accessibles à tous les utilisateurs du profil de travail, dans la [!DNL Profile Manager]section, cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
