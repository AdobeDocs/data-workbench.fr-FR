---
description: Les mappages de processus peuvent être configurés pour fonctionner avec n’importe quelle combinaison de dimension de base, de dimension de groupe, de dimension de niveau et de mesure qui convient à votre application et à votre jeu de données.
solution: Analytics
title: Configuration d’une carte de processus
topic: Data workbench
uuid: e629191e-48b9-4b58-b6aa-3705ff7b387e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuration d’une carte de processus{#configure-a-process-map}

Les mappages de processus peuvent être configurés pour fonctionner avec n’importe quelle combinaison de dimension de base, de dimension de groupe, de dimension de niveau et de mesure qui convient à votre application et à votre jeu de données.

Une fois que vous avez configuré un mappage de processus, il est répertorié avec d’autres mappages de processus dans le [!DNL Add Visualization menu].

1. Dans le [!DNL Profile Manager], cliquez sur **[!UICONTROL Menu]**, sur **[!UICONTROL Add Visualization]**, puis sur le type de mappage de processus à configurer (Carte de mesures 2D, Carte de processus 2D ou Carte de processus 3D).

   Au moins un [!DNL *.vw] fichier réside dans le répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche du fichier souhaité, puis cliquez sur **[!UICONTROL Make Local]**.
1. Cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Modifiez les paramètres du fichier à l’aide de l’exemple de fichier et du tableau suivants comme guides :

   ```
   window = simpleBorderWindow: 
     client = processMap: 
       Traffic Metric = ref: wdata/model/metric/metric name
       center = v3d: (-0.741014, 0, 0.0639476)
       color_links = bool: true
       Map = PrefixDim: 
         Name = string: Map
         Base Dimension = ref: wdata/model/dim/base dimension name
         Element Prefixes = vector: 0 items
         Element Names = vector: 0 items
       Map Level = ref: wdata/model/dim/level dimension name
       Map Group = ref: wdata/model/dim/group dimension name
       node_label = vector<bool>: 
       node_positions = vector: 0 items
       quantify_links = int: 2
       range = double: 2.37386
       size = v3d: (430, 290, 0)
       xAxisMetric = ref: wdata/model/metric/metric name for metric map
     pos = v3d: (880, 595, 0)
     size = v3d: (430, 309, 0)
   ```

<table id="table_3F072DB1B68746C49DF9332718982EBE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour ce paramètre... </th> 
   <th colname="col2" class="entry"> Fournissez ces informations... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><i>Nom de la mesure</i> </p> </td> 
   <td colname="col2"> <p>Nom de la mesure dont la valeur pour un noeud donné est proportionnelle à la taille du noeud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nom de la dimension de base</i> </p> </td> 
   <td colname="col2"> <p>Nom de la dimension dont les éléments apparaissent sous la forme de noeuds sur le mappage de processus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nom de la dimension de niveau</i> </p> </td> 
   <td colname="col2"> <p>Nom du niveau (parent) de la dimension de base dont vous faites glisser les éléments vers le mappage de processus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nom de la dimension du groupe</i> </p> </td> 
   <td colname="col2"> <p>Nom de la dimension qui détermine comment les éléments de la dimension de niveau sont regroupés pour former les connexions entre les noeuds. Une connexion entre deux noeuds ne peut pas couvrir plus d’un élément d’une dimension de groupe. Lorsque vous effectuez une sélection sur la base d’un noeud dans un mappage de processus, vous sélectionnez tous les éléments de la dimension de groupe qui impliquaient ce noeud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nom de la mesure pour la carte de mesure</i> </p> </td> 
   <td colname="col2"> <p>Ce paramètre s’applique uniquement aux cartes de mesures 2D. </p> <p>Nom de la mesure dont la valeur détermine la position horizontale des noeuds sur la carte. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Pour plus d’informations sur la dimension de base, la dimension de groupe, la dimension de niveau et la mesure d’un mappage de processus, voir [Process Maps](../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

1. Dans le Bloc-notes, cliquez sur **[!UICONTROL File]** > **[!UICONTROL Save As]** pour enregistrer le fichier sous un nouveau nom basé sur la dimension de base, c’est-à-dire le nom *de la dimension de* base.vw.

   (Si vous configurez un mappage de mesures 2D, vous devez enregistrer le fichier avec un nom basé sur le nom de la mesure pour le mappage de mesures, c’est-à-dire le nom de la *mesure pour le mappage* de mesures.vw.) Veillez à enregistrer le fichier dans le répertoire de mappage de processus approprié.

   >[!NOTE]
   >
   >Pour vous assurer que votre mappage de processus est enregistré en tant que [!DNL *.vw] fichier, dans la [!DNL Save As] fenêtre, définissez Enregistrer en tant que type sur Tous les fichiers.

1. (Facultatif) Pour rendre les modifications accessibles à tous les utilisateurs du profil de travail, dans la [!DNL Profile Manager]section, cliquez avec le bouton droit de la souris sur la coche du fichier dans la [!DNL User] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
