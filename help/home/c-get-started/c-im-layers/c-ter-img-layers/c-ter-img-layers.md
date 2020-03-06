---
description: Une couche d'image du terrain affiche l'imagerie du terrain de la Terre.
solution: Analytics
title: Calques d’image de terrain
topic: Data workbench
uuid: 17968293-1ad2-4040-a174-d33f418af9b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Calques d’image de terrain{#terrain-image-layers}

Une couche d&#39;image du terrain affiche l&#39;imagerie du terrain de la Terre.

[!DNL Terrain image layers] sont stockées dans le [!DNL Geography] profil dans un format personnalisé. Ces couches d’image peuvent être générées par Adobe, ou le serveur Outils de données peut transformer vos images de terrain fournies par l’utilisateur en couches de terrain adaptées à la visualisation sur le globe.

>[!NOTE]
>
>Pour travailler avec [!DNL terrain image layers], vous devez installer le [!DNL Terrain Images.cfg] fichier fourni par Adobe.

Pour définir un calque d’image de terrain, vous devez disposer des éléments suivants :

* **Un ou plusieurs fichiers** d’images de terrain contenant les images à afficher sur le globe.
* **Un[!DNL Terrain Images.cfg]fichier** qui spécifie le ou les fichiers image(s) de terrain à utiliser pour le ou les calques. Le [!DNL Terrain Images.cfg] fichier vous permet d&#39;ajouter une ou plusieurs sources pour créer une [!DNL terrain image layer]. Le format de votre fichier image de terrain détermine le type de source à ajouter. Le tableau suivant décrit les sources de calques d’images du terrain disponibles, y compris les formats de fichier d’images du terrain pris en charge :

<table id="table_CFDF5E61FCCD40B29A9D35FFA42F68D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Bitmap brut non projeté </p> </td> 
   <td colname="col2"> <p>Crée des calques <span class="wintitle"> d’image de</span> terrain à partir de fichiers RVB sans en-tête 24 bits alignés sur la latitude et la longitude (non projetés), où le nord est le haut de l’image et l’est la droite. </p> <p>Format(s) d’image(s) pris(s) en charge : RAW </p> <p> <p>Remarque : Cette source nécessite des informations de projection. Pour plus d’informations sur les formats de projection, voir <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Spécification des informations de projection pour les images</a>en relief. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Image générale, non projetée </p> </td> 
   <td colname="col2"> <p>Crée des calques <span class="wintitle"> d’image de</span> terrain à partir de formats d’image alignés sur la latitude et la longitude (non projetés) de 24 bits, où le nord est le haut de l’image et l’est la droite. </p> <p>Format(s) d’image(s) pris(s) en charge : BMP, JPG, PNG, TIFF </p> <p> <p>Remarque : Cette source nécessite des informations de projection. Pour plus d’informations sur les formats de projection, voir <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Spécification des informations de projection pour les images</a>en relief. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Image avec projection incorporée </p> </td> 
   <td colname="col2"> <p>Crée des calques <span class="wintitle"> d’image de</span> terrain à partir de formats d’image qui incorporent des données géodésiques dans le fichier image. Les informations de projection sont extraites de l’image. </p> <p>Format(s) d’image(s) pris(s) en charge : Erdas (IMG), GeoTIFF </p> <p> <p>Remarque : Cette source n'exige généralement pas d'information de projection, mais elle appuie l'ajout de cette information si nécessaire. Pour plus d’informations sur les formats de projection, voir <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Spécification des informations de projection pour les images</a>en relief. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Pour définir un calque d’image de terrain**

1. Dans Outils de données, dans l’onglet **[!UICONTROL Admin]** > **[!UICONTROL Dataset and Profile]** , cliquez sur la **[!UICONTROL Servers Manager]** vignette pour ouvrir l’ [!DNL Servers Manager] espace de travail.
1. Dans la [!DNL Servers Manager] fenêtre, cliquez avec le bouton droit de la souris sur l’icône du serveur Outils de données souhaité, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans la [!DNL Server Files Manager], cliquez **[!UICONTROL Components]** pour en afficher le contenu. Le [!DNL Terrain Images.cfg] fichier se trouve dans ce répertoire.
1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom du serveur [!DNL Terrain Images.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Terrain Images.cfg].
1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la **[!UICONTROL Temp]** colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La [!DNL Terrain Images.cfg] fenêtre s&#39;affiche.
1. Dans la [!DNL Terrain Images] fenêtre, cliquez **[!UICONTROL component]** pour en afficher le contenu.
1. Cliquez avec le bouton droit **[!UICONTROL Sources]** > **[!UICONTROL Add new]** , puis sélectionnez l’un des types de source suivants :

   * **[!UICONTROL Raw unprojected bitmap]**. (Une fois ajouté, ce type de source est intitulé RawTerrainSource dans la [!DNL Terrain Images] fenêtre.)

   * **[!UICONTROL General image, unprojected]**. (Une fois ajouté, ce type de source est libellé [!DNL GDALTerrainSource] dans la [!DNL Terrain Images] fenêtre.)

   * **[!UICONTROL Image with embedded projection]**. (Une fois ajouté, ce type de source est libellé [!DNL GDALTerrainSource] dans la [!DNL Terrain Images] fenêtre.)

1. Modifiez les paramètres de la source selon vos besoins à l’aide de l’exemple de fichier suivant et du tableau de paramètres sous forme de guides.

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
   <td colname="col2"> <p>Facultatif pour toutes les sources. Spécifie la correction gamma à appliquer à l’image source. Cela peut être souhaitable en raison du fait que les outils de données s’exécutent normalement avec un paramètre gamma élevé. La valeur par défaut est 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hauteur </p> </td> 
   <td colname="col2"> <p>Requis pour les images bitmap brutes non projetées. Hauteur de l’image source en pixels. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Infos sur la projection </p> </td> 
   <td colname="col2"> <p>Requis pour les images bitmap brutes non projetées et les images générales, non projetées, mais pris en charge pour les images avec projection incorporée. Les outils de données prennent en charge les projections latitude-longitude et les projections de Mercator transversal (TM) pour les couches d’image de terrain. Le format de projection par défaut est la projection latitude-longitude (LatLonProjection). </p> <p>Pour plus d’informations sur les formats de projection, voir <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Spécification des informations de projection pour les images</a>en relief. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Image source </p> </td> 
   <td colname="col2"> <p>Requis pour toutes les sources. Nom du fichier image source. Il peut s’agir d’un nom de fichier ou d’un modèle de caractères génériques. L’utilisation d’un modèle peut s’avérer utile si, par exemple, des images pour la même région à des dates différentes sont téléchargées, sans modification des métadonnées associées. Par conséquent, un modèle comme <span class="filepath"> Tysons Corner *.raw</span> créerait des calques à partir de <span class="filepath"> Tysons Corner 050211.raw</span>, de <span class="filepath"> Tysons Corner 050218.raw</span>, et ainsi de suite lorsque de nouvelles images sont ajoutées, sans configuration supplémentaire nécessaire si les paramètres des fichiers sont sinon identiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qualité de la compression des mosaïques </p> </td> 
   <td colname="col2"> <p>Facultatif pour toutes les sources. Pour la compression JPEG, nombre entier compris entre 0 et 100 indiquant comment équilibrer la taille et la qualité de l’image. (La valeur par défaut est zéro.) Un nombre plus élevé produit une meilleure qualité d’image, mais produit des images plus volumineuses et des temps de téléchargement plus longs pour les utilisateurs des outils de données. </p> <p> <p>Remarque :  La compression d’images inférieures à 70 peut entraîner une dégradation de l’image. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Compresseur de carreaux </p> </td> 
   <td colname="col2"> <p>Facultatif pour toutes les sources. Indique la méthode de compression utilisée pour écrire des fichiers de sortie. Les seules méthodes actuellement prises en charge sont RAWRGB (valeur par défaut, sans compression) et JPEG. Utilisez la compression JPEG pour réduire la taille des calques transmis lors de la synchronisation des profils. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Largeur </p> </td> 
   <td colname="col2"> <p>Requis pour les images bitmap brutes non projetées. Largeur de l’image source en pixels. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Modifiez les paramètres Emplacement de l’image source, Stockage des images temporaires et Ecrire les calques vers à l’aide du tableau suivant comme guide. Ces paramètres s’appliquent à toutes les sources d’images de terrain que vous définissez dans la [!DNL Sources] section de ce fichier.

<table id="table_103F02C54ED94C6C922450F5B2781CAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Emplacement de l'image source </p> </td> 
   <td colname="col2"> <p>Obligatoire. Répertoire numérisé pour les images à traduire en calques de terrain. S’il ne s’agit pas d’un chemin d’accès absolu, il est interprété par rapport au répertoire d’installation du serveur Outils de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stockage d’images temporaires </p> </td> 
   <td colname="col2"> <p>Facultatif. Nom d’un répertoire utilisé pour le stockage de fichiers temporaires utilisés dans la conversion des images source en calques de terrain. S’il ne s’agit pas d’un chemin d’accès absolu, il est interprété par rapport au répertoire d’installation du serveur Outils de données. L’emplacement par défaut est le répertoire <span class="wintitle"> Temp</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ecrire les calques dans </p> </td> 
   <td colname="col2"> <p>Obligatoire. Répertoire vers lequel les calques de terrain sont générés. Il s’agit généralement du sous-répertoire Maps d’un répertoire de profil, de sorte que la visualisation Globe puisse trouver les calques. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Enregistrez le fichier en cliquant avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et en cliquant sur **[!UICONTROL Save]**.
1. Pour enregistrer un fichier mis à jour sur l’ordinateur du serveur Outils de données, dans la [!DNL Server Files Manager]colonne, cliquez avec le bouton droit de la souris sur la coche [!DNL Terrain Images.cfg] de la [!DNL Temp] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

