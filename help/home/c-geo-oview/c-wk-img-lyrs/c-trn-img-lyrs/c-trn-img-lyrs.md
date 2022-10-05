---
description: Dans Data Workbench, une couche d’image du terrain affiche l’imagerie du terrain de la Terre.
title: Utilisation des calques d’image du terrain
uuid: 2f23a2c8-f551-4b84-bd87-5d7053910ab3
exl-id: 22026b41-4e12-4247-b019-461ae223bd07
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 2%

---

# Utilisation des calques d’image du terrain{#working-with-terrain-image-layers}

{{eol}}

Dans Data Workbench, une couche d’image du terrain affiche l’imagerie du terrain de la Terre.

Les calques d’image du terrain sont stockés dans la variable [!DNL Geography] dans un format personnalisé. Ces couches d’image peuvent être générées par Adobe ou le serveur Data Workbench peut transformer vos images du terrain fournies par l’utilisateur en couches de terrain adaptées à la visualisation du globe.

>[!NOTE]
>
>Pour travailler avec les calques d’image du terrain, vous devez installer le [!DNL Terrain Images.cfg] fichier fourni par Adobe. Pour obtenir des instructions sur l’installation, voir [Installation de Data Workbench Geography](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md).

Pour définir une couche d’image du terrain, vous devez disposer des éléments suivants :

* **Un ou plusieurs fichiers image du terrain** contenant les images à afficher sur le globe.
* **Une image du terrain.cfg** qui spécifie le ou les fichiers image(s) du terrain à utiliser pour le ou les calques. Le [!DNL Terrain Images.cfg] vous permet d’ajouter une ou plusieurs sources pour créer une couche d’image du terrain. Le format de votre fichier image du terrain détermine le type de source à ajouter. Le tableau suivant fournit des descriptions des sources de calque d’image du terrain disponibles, y compris les formats de fichiers d’image du terrain pris en charge :

<table id="table_BF8D5933BFBE45039BD164C258D3B450"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Image brute non projetée </td> 
   <td colname="col2"> <p>Crée des calques d’image du terrain à partir de fichiers RGB sans en-tête 24 bits alignés en latitude et longitude (non projetés), où nord est le haut de l’image et est la droite. </p> <p>Format(s) d’image pris en charge : RAW </p> <p> <p>Remarque : Cette source nécessite des informations de projection. Pour plus d’informations sur les formats de projection, voir <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Préciser les informations de projection des images du terrain</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Image générale, non projetée </td> 
   <td colname="col2"> <p>Crée des calques d’image du terrain à partir de formats d’image 24 bits alignés en latitude et longitude (non projetés), où le nord est le haut de l’image et l’est la droite. </p> <p>Format(s) d’image pris en charge : BMP, JPG, PNG, TIFF </p> <p> <p>Remarque : Cette source nécessite des informations de projection. Pour plus d’informations sur les formats de projection, voir <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Préciser les informations de projection des images du terrain</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Image avec projection incorporée </td> 
   <td colname="col2"> <p>Crée des calques d’image du terrain à partir de formats d’image qui intègrent des données géodésiques dans le fichier image. Les informations de projection sont extraites de l'image. </p> <p>Format(s) d’image pris en charge : Erdas (IMG), GeoTIFF </p> <p> <p>Remarque : En règle générale, cette source ne nécessite pas d’informations de projection, mais elle prend en charge l’ajout de telles informations si nécessaire. Pour plus d’informations sur les formats de projection, voir <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Préciser les informations de projection des images du terrain</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Pour définir un calque d’image du terrain**

1. Dans Data Workbench, sur la [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir la [!DNL Servers Manager] workspace.

1. Dans le [!DNL Servers Manager] cliquez avec le bouton droit de la souris sur l’icône du serveur Data Workbench souhaité, puis cliquez sur **[!UICONTROL Server Files]**.

1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour afficher son contenu. Le [!DNL Terrain Images.cfg] se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom de serveur pour [!DNL Terrain Images.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la variable [!DNL Temp] column pour [!DNL Terrain Images.cfg.]

1. Cliquez avec le bouton droit de la souris sur la coche nouvellement créée dans le [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Le [!DNL Terrain Images.cfg]s’affiche.

1. Dans le [!DNL Terrain Images] fenêtre, cliquez sur **[!UICONTROL component]** pour afficher son contenu.

1. Clic droit **[!UICONTROL Sources]** > **[!UICONTROL Add new]** et sélectionnez l’un des types de source suivants :

   * **[!UICONTROL Raw unprojected bitmap]**. (Une fois ajouté, ce type de source est intitulé RawTerrainSource dans la variable [!DNL Terrain Images] ).

   * **[!UICONTROL General image, unprojected]**. (Une fois ajouté, ce type de source est étiqueté GDALTerrainSource dans la variable [!DNL Terrain Images] ).

   * **[!UICONTROL Image with embedded projection]**. (Une fois ajouté, ce type de source est étiqueté GDALTerrainSource dans la variable [!DNL Terrain Images] ).

1. Modifiez les paramètres de la source selon les besoins à l&#39;aide de l&#39;exemple de fichier suivant et du tableau de paramètres comme guides.

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
   <td colname="col2"> Facultatif pour toutes les sources. Spécifie la correction gamma à appliquer à l’image source. Cela peut être souhaitable en raison du fait que Data Workbench s’exécute normalement avec un paramètre gamma élevé. La valeur par défaut est 1. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hauteur </td> 
   <td colname="col2"> Requis pour les images bitmap brutes non projetées. Hauteur de l’image source en pixels. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Infos sur la projection </td> 
   <td colname="col2"> <p>Requis pour les images bitmap brutes non projetées et les images générales, non projetées, mais pris en charge pour les images avec projection incorporée. Data Workbench<span class="wintitle"> Géographie</span> prend en charge les projections latitude-longitude et les projections Transverse Mercator (TM) pour les couches d’image du terrain. Le format de projection par défaut est la projection latitude-longitude (LatLonProjection). </p> <p>Pour plus d’informations sur les formats de projection, voir <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Préciser les informations de projection des images du terrain</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Image source </td> 
   <td colname="col2">Requis pour toutes les sources. Nom du fichier image source. Il peut s’agir d’un nom de fichier ou d’un caractère générique. L’utilisation d’un modèle peut s’avérer utile si, par exemple, des images d’une même région à des dates différentes sont chargées, sans modification des métadonnées associées. Par conséquent, un modèle comme "<span class="filepath"> Tysons Corner *.raw</span>" crée des calques à partir de <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>, etc. lors de l’ajout de nouvelles images, sans configuration supplémentaire nécessaire si les paramètres des fichiers sont identiques dans le cas contraire. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Qualité de compression des mosaïques </td> 
   <td colname="col2"> <p>Facultatif pour toutes les sources. Pour la compression JPEG, nombre entier compris entre 0 et 100 indiquant comment équilibrer la taille et la qualité de l’image. (La valeur par défaut est zéro.) Un nombre plus élevé se traduit par une meilleure qualité d’image, mais produit des images plus volumineuses et des temps de téléchargement plus longs pour les utilisateurs de Data Workbench. </p> <p>La compression d’images inférieures à 70 peut entraîner une dégradation de l’image. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mosaïque Compresseur </td> 
   <td colname="col2"> Facultatif pour toutes les sources. Indique la méthode de compression utilisée pour écrire des fichiers de sortie. Les seules méthodes actuellement prises en charge sont RAWRVB (valeur par défaut, sans compression) et JPEG. Utilisez la compression JPEG pour réduire la taille des calques transmis lors de la synchronisation des profils. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Largeur </td> 
   <td colname="col2"> Requis pour les images bitmap brutes non projetées. Largeur de l’image source en pixels. </td> 
  </tr> 
 </tbody> 
</table>

1. Modifiez les paramètres Emplacement de l’image source, Stockage de l’image temporaire et Écrire les calques vers à à l’aide du tableau suivant comme guide. Ces paramètres s’appliquent à toutes les sources d’images du terrain que vous définissez dans la section Sources de ce fichier.

   | Paramètre | Description |
   |---|---|
   | Emplacement de l’image source | Obligatoire. Répertoire qui recherche les images à traduire en couches de terrain. S’il ne s’agit pas d’un chemin d’accès absolu, il est interprété par rapport au répertoire d’installation du serveur Data Workbench. |
   | Stockage d’image temporaire | Facultatif. Nom d’un répertoire utilisé pour le stockage des fichiers temporaires utilisés dans la traduction des images sources en couches de terrain. S’il ne s’agit pas d’un chemin d’accès absolu, il est interprété par rapport au répertoire d’installation du serveur Data Workbench. L’emplacement par défaut est le répertoire Temp. |
   | Ecrire des calques sur | Obligatoire. Répertoire vers lequel les couches de terrain sont générées. Il s’agit généralement du sous-répertoire Maps d’un répertoire de profil, de sorte que la variable [!DNL Globe] la visualisation peut trouver les calques. |

1. Enregistrez le fichier en cliquant avec le bouton droit de la souris **[!UICONTROL (modified)]** en haut de la fenêtre et en cliquant sur **[!UICONTROL Save]**.

1. Pour enregistrer le fichier mis à jour sur l’ordinateur du serveur Data Workbench, dans la variable [!DNL Server Files Manager], cliquez avec le bouton droit de la souris sur la coche pour [!DNL Terrain Images.cfg] dans le [!DNL Temp] , puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
