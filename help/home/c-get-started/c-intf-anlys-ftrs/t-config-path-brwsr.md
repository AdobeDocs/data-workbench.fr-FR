---
description: Les navigateurs de chemins d’accès peuvent être configurés pour fonctionner avec n’importe quelle combinaison de dimension de base, de dimension de groupe, de dimension de niveau et de mesure adaptée à votre application et à votre jeu de données.
title: Configuration d’un navigateur de chemins d’accès
uuid: 1ba3fb6e-b76f-428f-b6ec-077669c3b305
exl-id: be6a68f7-e3e3-4207-a112-3a4fdd5c5f57
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 1%

---

# Configuration d’un navigateur de chemins d’accès{#configure-a-path-browser}

{{eol}}

Les navigateurs de chemins d’accès peuvent être configurés pour fonctionner avec n’importe quelle combinaison de dimension de base, de dimension de groupe, de dimension de niveau et de mesure adaptée à votre application et à votre jeu de données.

Une fois que vous avez configuré un navigateur de chemins d’accès, il est répertorié avec d’autres navigateurs de chemins d’accès dans la [!DNL Add Visualization] .

1. Dans le [!DNL Profile Manager], cliquez sur **[!UICONTROL Menu]**, puis cliquez sur **[!UICONTROL Add Visualization]** et **[!UICONTROL Path Browser]**.

   Au moins un [!DNL *.vw] réside dans le répertoire de l’Explorateur de chemins d’accès.

1. Cliquez avec le bouton droit de la souris sur la coche du fichier souhaité, puis cliquez sur **[!UICONTROL Make Local]**.
1. Cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Editez les paramètres du fichier à l&#39;aide de l&#39;exemple de fichier et du tableau ci-dessous sous forme de guides :

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
   <td colname="col2"> <p>Nom de la dimension dont les éléments apparaissent dans l’explorateur de chemins d’accès. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nom de la dimension du groupe</i> </p> </td> 
   <td colname="col2"> <p>Nom de la dimension qui détermine le mode de regroupement des éléments de la dimension de niveau pour former les chemins dans un navigateur de chemins d’accès. En particulier, les éléments de dimension de niveau associés à un seul chemin dans un navigateur de chemins d’accès ne peuvent pas couvrir plusieurs éléments d’une dimension de groupe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nom de la dimension de niveau</i> </p> </td> 
   <td colname="col2"> <p>Nom du niveau (parent) de la dimension de base dont vous faites glisser les éléments vers l’explorateur de chemins d’accès. Lorsque vous suivez un chemin d’un élément de dimension de base à un autre, vous passez d’un élément de dimension de niveau à un autre. Lorsque vous sélectionnez un chemin d’accès d’éléments de dimension de base, vous sélectionnez des données pour les éléments correspondants de la dimension de niveau. La sélection inclut toujours les éléments de la dimension de niveau qui se rapportent à la racine. Elle est affinée en ajoutant d’autres éléments au chemin. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nom de la mesure</i> </p> </td> 
   <td colname="col2"> <p>Nom de la mesure dont la valeur pour un élément donné est proportionnelle à l’épaisseur du chemin conduisant à cet élément. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Pour plus d’informations sur la dimension de base, la dimension de groupe, la dimension de niveau et la mesure pour un navigateur de chemins d’accès, voir [Navigateurs de chemins d’accès](../../../home/c-get-started/c-analysis-vis/c-path-browsers/c-path-browsers.md#concept-f2e9fdafed6e49c2bd111ab425cd6e2b).

1. Dans Notepad, cliquez sur **[!UICONTROL File]** > **[!UICONTROL Save As]** pour enregistrer le fichier avec un nouveau nom basé sur la dimension de groupe, c’est-à-dire : *Nom de la dimension du groupe*.vw.

   Veillez à enregistrer le fichier dans le répertoire de l’explorateur de chemins d’accès.

   >[!NOTE]
   >
   >Pour vous assurer que votre navigateur de chemins d’accès est enregistré en tant que [!DNL *.vw] , dans le fichier [!DNL Save As] , définissez Enregistrer comme type sur Tous les fichiers.

1. (Facultatif) Pour mettre les modifications à la disposition de tous les utilisateurs du profil de travail, dans la variable [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la variable [!DNL User] et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
