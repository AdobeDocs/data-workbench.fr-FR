---
description: Les mappages de processus peuvent être configurés pour fonctionner avec n’importe quelle combinaison de dimension de base, de dimension de groupe, de dimension de niveau et de mesure pertinente pour votre application et votre jeu de données.
title: Configuration d’une cartographie des processus
uuid: e629191e-48b9-4b58-b6aa-3705ff7b387e
exl-id: 0b37e942-4596-45cc-bc31-db147626f4eb
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 2%

---

# Configuration d’une cartographie des processus{#configure-a-process-map}

Les mappages de processus peuvent être configurés pour fonctionner avec n’importe quelle combinaison de dimension de base, de dimension de groupe, de dimension de niveau et de mesure pertinente pour votre application et votre jeu de données.

Une fois que vous avez configuré une cartographie des processus, elle est répertoriée avec d’autres mappages de processus dans la balise [!DNL Add Visualization menu].

1. Dans la balise [!DNL Profile Manager], cliquez sur **[!UICONTROL Menu]**, cliquez sur **[!UICONTROL Add Visualization]**, puis sur le type de mappage de processus que vous souhaitez configurer (Carte des mesures 2D, Carte des processus 2D ou Carte des processus 3D).

   Au moins un fichier [!DNL *.vw] réside dans le répertoire .

1. Cliquez avec le bouton droit de la souris sur la coche du fichier souhaité, puis cliquez sur **[!UICONTROL Make Local]**.
1. Cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL User] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Editez les paramètres du fichier à l&#39;aide de l&#39;exemple de fichier et du tableau ci-dessous sous forme de guides :

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
   <td colname="col2"> <p>Nom de la dimension dont les éléments apparaissent sous la forme de noeuds sur la cartographie des processus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nom de la dimension de niveau</i> </p> </td> 
   <td colname="col2"> <p>Nom du niveau (parent) de la dimension de base dont vous faites glisser les éléments vers la cartographie des processus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nom de la dimension du groupe</i> </p> </td> 
   <td colname="col2"> <p>Nom de la dimension qui détermine la manière dont les éléments de la dimension de niveau sont regroupés pour former les connexions entre les noeuds. Une connexion entre deux noeuds ne peut pas couvrir plusieurs éléments d’une dimension de groupe. Lorsque vous effectuez une sélection en fonction d’un noeud dans une cartographie des processus, vous sélectionnez tous les éléments de la dimension de groupe qui ont impliqué ce noeud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><i>Nom de mesure pour la carte de mesures</i> </p> </td> 
   <td colname="col2"> <p>Ce paramètre s’applique uniquement aux cartes de mesures 2D. </p> <p>Nom de la mesure dont la valeur détermine la position horizontale des noeuds sur la carte. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Pour plus d’informations sur la dimension de base, la dimension de groupe, la dimension de niveau et la mesure pour une cartographie des processus, voir [Cartes des processus](../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

1. Dans le Bloc-notes, cliquez sur **[!UICONTROL File]** > **[!UICONTROL Save As]** pour enregistrer le fichier avec un nouveau nom basé sur la dimension de base, c’est-à-dire *Nom de la dimension de base*.vw.

   (Si vous configurez une carte de mesure 2D, vous devez enregistrer le fichier avec un nom basé sur le nom de mesure de la carte de mesure, c’est-à-dire *nom de mesure pour la carte de mesure*.vw.) Veillez à enregistrer le fichier dans le répertoire de cartographie des processus approprié.

   >[!NOTE]
   >
   >Pour vous assurer que votre cartographie des processus est enregistrée en tant que fichier [!DNL *.vw], dans la fenêtre [!DNL Save As], définissez Enregistrer en tant que type sur Tous les fichiers.

1. (Facultatif) Pour mettre les modifications à la disposition de tous les utilisateurs du profil de travail, dans la balise [!DNL Profile Manager], cliquez avec le bouton droit de la souris sur la coche du fichier dans la colonne [!DNL User] et cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***.
