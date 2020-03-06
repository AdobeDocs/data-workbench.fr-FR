---
description: Dans les outils de données, une couche d’image de terrain affiche l’imagerie de terrain de la Terre.
solution: Analytics
title: Utilisation des calques d’image Terrain
topic: Data workbench
uuid: 2f23a2c8-f551-4b84-bd87-5d7053910ab3
translation-type: tm+mt
source-git-commit: 948c6dd04819e939b45745db573a53c8be51ce37

---


# Utilisation des calques d’image Terrain{#working-with-terrain-image-layers}

Dans les outils de données, une couche d’image de terrain affiche l’imagerie de terrain de la Terre.

Les calques d’image de terrain sont stockés dans le [!DNL Geography] profil, dans un format personnalisé. Ces couches d’image peuvent être générées par Adobe, ou le serveur des outils de données peut transformer vos images de terrain fournies par l’utilisateur en couches de terrain adaptées à la visualisation sur le globe.

>[!NOTE]
>
>Pour utiliser les calques d’image de terrain, vous devez installer le [!DNL Terrain Images.cfg] fichier fourni par Adobe. Pour plus d’informations sur l’installation, voir [Installation de la géographie](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md)des outils de données.

Pour définir un calque d’image de terrain, vous devez disposer des éléments suivants :

* **Un ou plusieurs fichiers** d’images de terrain contenant les images à afficher sur le globe.
* **Fichier Terrain Images.cfg** qui spécifie le ou les fichiers d’image de terrain à utiliser pour le ou les calques. Le [!DNL Terrain Images.cfg] fichier vous permet d’ajouter une ou plusieurs sources pour créer un calque d’image de terrain. Le format de votre fichier image de terrain détermine le type de source à ajouter. Le tableau suivant décrit les sources de calques d’images du terrain disponibles, y compris les formats de fichier d’images du terrain pris en charge :

<table id="table_BF8D5933BFBE45039BD164C258D3B450"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Bitmap brut non projeté </td> 
   <td colname="col2"> <p>Crée des calques d’image de terrain à partir de fichiers RVB sans en-tête 24 bits alignés sur la latitude et la longitude (non projetés), où le nord est le haut de l’image et l’est la droite. </p> <p>Format(s) d’image(s) pris(s) en charge : RAW </p> <p> <p>Remarque : Cette source nécessite des informations de projection. Pour plus d’informations sur les formats de projection, voir <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Spécification des informations de projection pour les images</a>en relief. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Image générale, non projetée </td> 
   <td colname="col2"> <p>Crée des calques d’image de terrain à partir de formats d’image alignés sur la latitude et la longitude (non projetés) de 24 bits, où le nord est le haut de l’image et l’est la droite. </p> <p>Format(s) d’image(s) pris(s) en charge : BMP, JPG, PNG, TIFF </p> <p> <p>Remarque : Cette source nécessite des informations de projection. Pour plus d’informations sur les formats de projection, voir <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Spécification des informations de projection pour les images</a>en relief. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Image avec projection incorporée </td> 
   <td colname="col2"> <p>Crée des calques d’image de terrain à partir de formats d’image qui incorporent des données géodésiques dans le fichier image. Les informations de projection sont extraites de l’image. </p> <p>Format(s) d’image(s) pris(s) en charge : Erdas (IMG), GeoTIFF </p> <p> <p>Remarque : Cette source n'exige généralement pas d'information de projection, mais elle appuie l'ajout de cette information si nécessaire. Pour plus d’informations sur les formats de projection, voir <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Spécification des informations de projection pour les images</a>en relief. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Pour définir un calque d’image de terrain**

1. Dans l’outil de données, dans l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** vignette pour ouvrir l’ [!DNL Servers Manager] espace de travail.

1. Dans la [!DNL Servers Manager] fenêtre, cliquez avec le bouton droit de la souris sur l’icône du serveur de l’outil de données souhaité, puis cliquez sur **[!UICONTROL Server Files]**.

1. Dans la [!DNL Server Files Manager], cliquez **[!UICONTROL Components]** pour en afficher le contenu. Le [!DNL Terrain Images.cfg] fichier se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom du serveur [!DNL Terrain Images.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la [!DNL Temp] colonne pour [!DNL Terrain Images.cfg.]

1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la [!DNL Temp] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La [!DNL Terrain Images.cfg]fenêtre s&#39;affiche.

1. Dans la [!DNL Terrain Images] fenêtre, cliquez **[!UICONTROL component]** pour en afficher le contenu.

1. Cliquez avec le bouton droit **[!UICONTROL Sources]** > **[!UICONTROL Add new]** , puis sélectionnez l’un des types de source suivants :

   * **[!UICONTROL Raw unprojected bitmap]**. (Une fois ajouté, ce type de source est intitulé RawTerrainSource dans la [!DNL Terrain Images] fenêtre.)

   * **[!UICONTROL General image, unprojected]**. (Une fois ajouté, ce type de source est intitulé GDALTerrainSource dans la [!DNL Terrain Images] fenêtre.)

   * **[!UICONTROL Image with embedded projection]**. (Une fois ajouté, ce type de source est intitulé GDALTerrainSource dans la [!DNL Terrain Images] fenêtre.)

1. Modifiez les paramètres de la source selon vos besoins à l’aide de l’exemple de fichier suivant et du tableau de paramètres sous forme de guides.

   ![](assets/cfg_TerrainImages_ALL.png)

<table id="table_83171CB58F8B4816BCCA9BFFD5ECD92A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> Facultatif pour toutes les sources. Spécifie la correction gamma à appliquer à l’image source. Cela peut être souhaitable en raison du fait que les outils de données s’exécutent normalement avec un paramètre gamma élevé. La valeur par défaut est 1. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hauteur </td> 
   <td colname="col2"> Requis pour les images bitmap brutes non projetées. Hauteur de l’image source en pixels. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Infos sur la projection </td> 
   <td colname="col2"> <p>Requis pour les images bitmap brutes non projetées et les images générales, non projetées, mais pris en charge pour les images avec projection incorporée. La géographie des outils<span class="wintitle"> de données</span> prend en charge les projections latitude-longitude et les projections de Mercator transversal (TM) pour les couches d’image de terrain. Le format de projection par défaut est la projection latitude-longitude (LatLonProjection). </p> <p>Pour plus d’informations sur les formats de projection, voir <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Spécification des informations de projection pour les images</a>en relief. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Image source </td> 
   <td colname="col2">Requis pour toutes les sources. Nom du fichier image source. Il peut s’agir d’un nom de fichier ou d’un modèle de caractères génériques. L’utilisation d’un modèle peut s’avérer utile si, par exemple, des images pour la même région à des dates différentes sont téléchargées, sans modification des métadonnées associées. Par conséquent, un modèle comme "<span class="filepath"> Tysons Corner *.raw</span>" créerait des calques à partir de <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>, et ainsi de suite lorsque de nouvelles images sont ajoutées, sans configuration supplémentaire nécessaire si les paramètres des fichiers sont sinon identiques. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Qualité de la compression des mosaïques </td> 
   <td colname="col2"> <p>Facultatif pour toutes les sources. Pour la compression JPEG, nombre entier compris entre 0 et 100 indiquant comment équilibrer la taille et la qualité de l’image. (La valeur par défaut est zéro.) Un nombre plus élevé produit une meilleure qualité d’image, mais produit des images plus volumineuses et des temps de téléchargement plus longs pour les utilisateurs des outils de données. </p> <p>La compression d’images inférieures à 70 peut entraîner une dégradation de l’image. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compresseur de carreaux </td> 
   <td colname="col2"> Facultatif pour toutes les sources. Indique la méthode de compression utilisée pour écrire des fichiers de sortie. Les seules méthodes actuellement prises en charge sont RAWRGB (valeur par défaut, sans compression) et JPEG. Utilisez la compression JPEG pour réduire la taille des calques transmis lors de la synchronisation des profils. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Largeur </td> 
   <td colname="col2"> Requis pour les images bitmap brutes non projetées. Largeur de l’image source en pixels. </td> 
  </tr> 
 </tbody> 
</table>

1. Modifiez les paramètres Emplacement de l’image source, Stockage des images temporaires et Ecrire les calques vers à l’aide du tableau suivant comme guide. Ces paramètres s’appliquent à toutes les sources d’images de terrain que vous définissez dans la section Sources de ce fichier.

   | Paramètre | Description |
   |---|---|
   | Emplacement de l&#39;image source | Obligatoire. Répertoire numérisé pour les images à traduire en calques de terrain. S’il ne s’agit pas d’un chemin d’accès absolu, il est interprété par rapport au répertoire d’installation du serveur de l’outil de données. |
   | Stockage d’images temporaires | Facultatif. Nom d’un répertoire utilisé pour le stockage de fichiers temporaires utilisés dans la conversion des images source en calques de terrain. S’il ne s’agit pas d’un chemin d’accès absolu, il est interprété par rapport au répertoire d’installation du serveur de l’outil de données. L’emplacement par défaut est le répertoire Temp. |
   | Ecrire les calques dans | Obligatoire. Répertoire vers lequel les calques de terrain sont générés. Il s’agit généralement du sous-répertoire Maps d’un répertoire de profil, de sorte que la [!DNL Globe] visualisation puisse trouver les calques. |

1. Enregistrez le fichier en cliquant avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et en cliquant sur **[!UICONTROL Save]**.

1. Pour enregistrer le fichier mis à jour sur l’ordinateur serveur de l’outil de données, dans la [!DNL Server Files Manager]colonne, cliquez avec le bouton droit de la souris sur la coche [!DNL Terrain Images.cfg] de la [!DNL Temp] colonne, puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

