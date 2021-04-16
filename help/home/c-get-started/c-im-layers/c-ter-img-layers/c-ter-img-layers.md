---
description: Une couche d'image de terrain affiche l'imagerie de terrain de la Terre.
title: Calques d’image du terrain
uuid: 17968293-1ad2-4040-a174-d33f418af9b7
exl-id: 754211a7-0b1f-4353-86f8-9c634d70cd83
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 2%

---

# Calques d’image du terrain{#terrain-image-layers}

Une couche d&#39;image de terrain affiche l&#39;imagerie de terrain de la Terre.

[!DNL Terrain image layers] sont stockées dans le  [!DNL Geography] profil dans un format personnalisé. Ces couches d&#39;image peuvent être générées par Adobe ou le serveur Data Workbench peut transformer vos images de terrain fournies par l&#39;utilisateur en couches de terrain adaptées à la visualisation sur le globe.

>[!NOTE]
>
>Pour utiliser [!DNL terrain image layers], vous devez installer le fichier [!DNL Terrain Images.cfg] fourni par l&#39;Adobe.

Pour définir un calque d’image de terrain, vous devez disposer des éléments suivants :

* **Un ou plusieurs** fichiers d’images de terrain contenant les images à afficher sur le globe.
* **Un  [!DNL Terrain Images.cfg]** fichier qui spécifie le ou les fichiers d&#39;image de terrain à utiliser pour le ou les calques. Le fichier [!DNL Terrain Images.cfg] vous permet d&#39;ajouter une ou plusieurs sources pour créer une [!DNL terrain image layer]. Le format de votre fichier d&#39;image de terrain détermine le type de source à ajouter. Le tableau suivant fournit des descriptions des sources de calques d&#39;image de terrain disponibles, y compris les formats de fichier d&#39;image de terrain pris en charge :

<table id="table_CFDF5E61FCCD40B29A9D35FFA42F68D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Image brute non projetée </p> </td> 
   <td colname="col2"> <p>Crée <span class="wintitle"> couches d’image de relief</span> à partir de fichiers RVB 24 bits sans en-tête alignés par latitude et longitude (non projetés), où le nord est le haut de l’image et l’est la droite. </p> <p>Format(s) d’image pris en charge : RAW </p> <p> <p>Remarque : Cette source nécessite des informations de projection. Pour plus d'informations sur les formats de projection, voir <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Spécification des informations de projection pour les images de terrain</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Image générale, non projetée </p> </td> 
   <td colname="col2"> <p>Crée <span class="wintitle"> couches d’image de relief</span> à partir de formats d’image alignés sur la latitude et la longitude (non projetés) de 24 bits, où le nord est le haut de l’image et l’est la droite. </p> <p>Format(s) d’image pris en charge : BMP, JPG, PNG, TIFF </p> <p> <p>Remarque : Cette source nécessite des informations de projection. Pour plus d'informations sur les formats de projection, voir <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Spécification des informations de projection pour les images de terrain</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Image avec projection incorporée </p> </td> 
   <td colname="col2"> <p>Crée <span class="wintitle"> couches d’image de relief</span> à partir de formats d’image qui incorporent des données géodésiques dans le fichier image. L'information de projection est extraite de l'image. </p> <p>Format(s) d’image pris en charge : Erdas (IMG), GeoTIFF </p> <p> <p>Remarque : Cette source n'exige généralement pas d'information de projection, mais appuie l'ajout de cette information si nécessaire. Pour plus d'informations sur les formats de projection, voir <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Spécification des informations de projection pour les images de terrain</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Pour définir un calque d’image de relief**

1. En Data Workbench, sur l&#39;onglet **[!UICONTROL Admin]** > **[!UICONTROL Dataset and Profile]**, cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l&#39;espace de travail [!DNL Servers Manager].
1. Dans la fenêtre [!DNL Servers Manager], cliquez avec le bouton droit de la souris sur l&#39;icône du serveur de Data Workbench de votre choix et cliquez sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour en vue le contenu. Le fichier [!DNL Terrain Images.cfg] se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom de serveur pour [!DNL Terrain Images.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la colonne [!DNL Temp] pour [!DNL Terrain Images.cfg].
1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la colonne **[!UICONTROL Temp]** et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La fenêtre [!DNL Terrain Images.cfg] s&#39;affiche.
1. Dans la fenêtre [!DNL Terrain Images], cliquez sur **[!UICONTROL component]** pour en vue le contenu.
1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL Sources]** > **[!UICONTROL Add new]** et choisissez l’un des types de source suivants :

   * **[!UICONTROL Raw unprojected bitmap]**. (Une fois ajouté, ce type de source est intitulé RawTerrainSource dans la fenêtre [!DNL Terrain Images].)

   * **[!UICONTROL General image, unprojected]**. (Une fois ajouté, ce type de source est intitulé [!DNL GDALTerrainSource] dans la fenêtre [!DNL Terrain Images].)

   * **[!UICONTROL Image with embedded projection]**. (Une fois ajouté, ce type de source est intitulé [!DNL GDALTerrainSource] dans la fenêtre [!DNL Terrain Images].)

1. Modifiez les paramètres de la source si nécessaire en utilisant le fichier d&#39;exemple suivant et le tableau de paramètres comme guides.

   ![](assets/cfg_TerrainImages_ALL.png)

<table id="table_345ACB4C48524516AADB731D87FC6792"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> <p>Facultatif pour toutes les sources. Spécifie la correction gamma à appliquer à l’image source. Cela peut être souhaitable car le Data Workbench fonctionne normalement avec un paramètre gamma élevé. La valeur par défaut est 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hauteur </p> </td> 
   <td colname="col2"> <p>Requis pour les images bitmap brutes non projetées. Hauteur de l’image source en pixels. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Infos sur la projection </p> </td> 
   <td colname="col2"> <p>Requis pour les images bitmap brutes non projetées et les images générales, non projetées, mais pris en charge pour les images avec projection incorporée. Le Data Workbench prend en charge les projections latitude-longitude et les projections de Mercator transversal (TM) pour les couches d'image de terrain. Le format de projection par défaut est la projection latitude-longitude (LatLonProjection). </p> <p>Pour plus d'informations sur les formats de projection, voir <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Spécification des informations de projection pour les images de terrain</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Image source </p> </td> 
   <td colname="col2"> <p>Requis pour toutes les sources. Nom du fichier image source. Il peut s’agir d’un nom de fichier ou d’un modèle générique. L’utilisation d’un modèle peut s’avérer utile si, par exemple, des images pour la même région à des dates différentes sont téléchargées, sans modification des métadonnées associées. Par conséquent, un modèle tel que <span class="filepath"> Tysons Corner *.raw</span> créerait des calques à partir de <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>, et ainsi de suite lorsque de nouvelles images sont ajoutées, sans configuration supplémentaire nécessaire si les paramètres de dans le cas contraire, les fichiers sont identiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qualité de la compression des mosaïques </p> </td> 
   <td colname="col2"> <p>Facultatif pour toutes les sources. Pour la compression JPEG, entier compris entre 0 et 100 indiquant comment équilibrer la taille et la qualité de l’image. (La valeur par défaut est zéro.) Un nombre plus élevé produit une meilleure qualité d’image, mais produit des images plus volumineuses et des temps de téléchargement plus longs pour les utilisateurs Data Workbench. </p> <p> <p>Remarque :  La compression d’images inférieures à 70 peut entraîner la dégradation de l’image. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Compresseur de mosaïque </p> </td> 
   <td colname="col2"> <p>Facultatif pour toutes les sources. Indique la méthode de compression utilisée pour écrire les fichiers de sortie. Les seules méthodes actuellement prises en charge sont RAWRGB (valeur par défaut, sans compression) et JPEG. Utilisez la compression JPEG pour réduire la taille des calques transmis lors de la synchronisation des profils. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Largeur </p> </td> 
   <td colname="col2"> <p>Requis pour les images bitmap brutes non projetées. Largeur de l’image source en pixels. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Modifiez les paramètres Emplacement de l’image source, Enregistrement d’image temporaire et Ecrire les calques en utilisant le tableau suivant comme guide. Ces paramètres s&#39;appliquent à toutes les sources d&#39;image de terrain que vous définissez dans la section [!DNL Sources] de ce fichier.

<table id="table_103F02C54ED94C6C922450F5B2781CAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Emplacement de l’image source </p> </td> 
   <td colname="col2"> <p>Obligatoire. Répertoire qui est analysé pour rechercher des images à traduire en couches de terrain. S’il ne s’agit pas d’un chemin d’accès absolu, il est interprété par rapport au répertoire d’installation du serveur Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enregistrement d’image temporaire </p> </td> 
   <td colname="col2"> <p>Facultatif. Nom d’un répertoire utilisé pour l’enregistrement de fichiers temporaires utilisés dans la traduction d’images source vers des couches de terrain. S’il ne s’agit pas d’un chemin d’accès absolu, il est interprété par rapport au répertoire d’installation du serveur Data Workbench. L’emplacement par défaut est le répertoire <span class="wintitle"> Temp</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ecrire des calques sur </p> </td> 
   <td colname="col2"> <p>Obligatoire. Répertoire vers lequel les couches de terrain sont produites. Il s’agit généralement du sous-répertoire Maps d’un répertoire de profil, de sorte que la visualisation Globe puisse trouver les calques. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Enregistrez le fichier en cliquant avec le bouton droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre et en cliquant sur **[!UICONTROL Save]**.
1. Pour enregistrer un fichier mis à jour sur l&#39;ordinateur du serveur Data Workbench, dans le [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche [!DNL Terrain Images.cfg] dans la colonne [!DNL Temp], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.
