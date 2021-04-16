---
description: Dans les outils de données, une couche d’image de terrain affiche l’imagerie de terrain de la Terre.
title: Utilisation des calques d’image du terrain
uuid: 2f23a2c8-f551-4b84-bd87-5d7053910ab3
exl-id: 22026b41-4e12-4247-b019-461ae223bd07
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 2%

---

# Utilisation des calques d’image du terrain{#working-with-terrain-image-layers}

Dans les outils de données, une couche d’image de terrain affiche l’imagerie de terrain de la Terre.

Les calques d’image de terrain sont stockés dans le profil [!DNL Geography], dans un format personnalisé. Ces couches d’image peuvent être générées par Adobe ou le serveur de pupitre de données peut transformer vos images de terrain fournies par l’utilisateur en couches de terrain adaptées à la visualisation sur le globe.

>[!NOTE]
>
>Pour utiliser les couches d&#39;image de relief, vous devez installer le fichier [!DNL Terrain Images.cfg] fourni par Adobe. Pour obtenir des instructions sur l&#39;installation, voir [Installation de la géographie du Data Workbench](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md).

Pour définir un calque d’image de terrain, vous devez disposer des éléments suivants :

* **Un ou plusieurs** fichiers d’images de terrain contenant les images à afficher sur le globe.
* **Un fichier Terrain Images.** cfgfile qui spécifie le ou les fichiers image(s) de terrain à utiliser pour les calques. Le fichier [!DNL Terrain Images.cfg] vous permet d&#39;ajouter une ou plusieurs sources pour créer une couche d&#39;image de terrain. Le format de votre fichier d&#39;image de terrain détermine le type de source à ajouter. Le tableau suivant fournit des descriptions des sources de calques d&#39;image de terrain disponibles, y compris les formats de fichier d&#39;image de terrain pris en charge :

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
   <td colname="col2"> <p>Crée des couches d’image de terrain à partir de fichiers RVB sans en-tête de 24 bits alignés sur la latitude et la longitude (non projetés), où le nord est le haut de l’image et l’est la droite. </p> <p>Format(s) d’image pris en charge : RAW </p> <p> <p>Remarque : Cette source nécessite des informations de projection. Pour plus d'informations sur les formats de projection, voir <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Spécification des informations de projection pour les images de terrain</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Image générale, non projetée </td> 
   <td colname="col2"> <p>Crée des couches d’image de terrain à partir de formats d’image alignés sur la latitude et la longitude (non projetés) de 24 bits, où le nord est le haut de l’image et l’est la droite. </p> <p>Format(s) d’image pris en charge : BMP, JPG, PNG, TIFF </p> <p> <p>Remarque : Cette source nécessite des informations de projection. Pour plus d'informations sur les formats de projection, voir <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Spécification des informations de projection pour les images de terrain</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Image avec projection incorporée </td> 
   <td colname="col2"> <p>Crée des calques d’image de relief à partir de formats d’image qui incorporent des données géodésiques dans le fichier image. L'information de projection est extraite de l'image. </p> <p>Format(s) d’image pris en charge : Erdas (IMG), GeoTIFF </p> <p> <p>Remarque : Cette source n'exige généralement pas d'information de projection, mais appuie l'ajout de cette information si nécessaire. Pour plus d'informations sur les formats de projection, voir <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Spécification des informations de projection pour les images de terrain</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Pour définir un calque d’image de relief**

1. Dans l’outil de données, sous l’onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l’espace de travail [!DNL Servers Manager].

1. Dans la fenêtre [!DNL Servers Manager], cliquez avec le bouton droit de la souris sur l&#39;icône du serveur de l&#39;outil de données de votre choix, puis cliquez sur **[!UICONTROL Server Files]**.

1. Dans le [!DNL Server Files Manager], cliquez sur **[!UICONTROL Components]** pour en vue le contenu. Le fichier [!DNL Terrain Images.cfg] se trouve dans ce répertoire.

1. Cliquez avec le bouton droit de la souris sur la coche dans la colonne du nom de serveur pour [!DNL Terrain Images.cfg], puis cliquez sur **[!UICONTROL Make Local]**. Une coche apparaît dans la colonne [!DNL Temp] pour [!DNL Terrain Images.cfg.]

1. Cliquez avec le bouton droit sur la coche nouvellement créée dans la colonne [!DNL Temp] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La fenêtre [!DNL Terrain Images.cfg]s&#39;affiche.

1. Dans la fenêtre [!DNL Terrain Images], cliquez sur **[!UICONTROL component]** pour en vue le contenu.

1. Cliquez avec le bouton droit de la souris sur **[!UICONTROL Sources]** > **[!UICONTROL Add new]** et choisissez l’un des types de source suivants :

   * **[!UICONTROL Raw unprojected bitmap]**. (Une fois ajouté, ce type de source est intitulé RawTerrainSource dans la fenêtre [!DNL Terrain Images].)

   * **[!UICONTROL General image, unprojected]**. (Une fois ajouté, ce type de source est intitulé GDALTerrainSource dans la fenêtre [!DNL Terrain Images].)

   * **[!UICONTROL Image with embedded projection]**. (Une fois ajouté, ce type de source est intitulé GDALTerrainSource dans la fenêtre [!DNL Terrain Images].)

1. Modifiez les paramètres de la source si nécessaire en utilisant le fichier d&#39;exemple suivant et le tableau de paramètres comme guides.

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
   <td colname="col2"> Facultatif pour toutes les sources. Spécifie la correction gamma à appliquer à l’image source. Cela peut s’avérer souhaitable en raison du fait que les outils de données s’exécutent normalement avec un paramètre gamma élevé. La valeur par défaut est 1. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hauteur </td> 
   <td colname="col2"> Requis pour les images bitmap brutes non projetées. Hauteur de l’image source en pixels. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Infos sur la projection </td> 
   <td colname="col2"> <p>Requis pour les images bitmap brutes non projetées et les images générales, non projetées, mais pris en charge pour les images avec projection incorporée. Les outils de données<span class="wintitle"> Géographie</span> prennent en charge les projections latitude-longitude et les projections de Mercator transversal (TM) pour les couches d'image de terrain. Le format de projection par défaut est la projection latitude-longitude (LatLonProjection). </p> <p>Pour plus d'informations sur les formats de projection, voir <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Spécification des informations de projection pour les images de terrain</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Image source </td> 
   <td colname="col2">Requis pour toutes les sources. Nom du fichier image source. Il peut s’agir d’un nom de fichier ou d’un modèle générique. L’utilisation d’un modèle peut s’avérer utile si, par exemple, des images pour la même région à des dates différentes sont téléchargées, sans modification des métadonnées associées. Par conséquent, un modèle du type "<span class="filepath"> Tysons Corner *.raw</span>" créerait des couches à partir de <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>, et ainsi de suite lorsque de nouvelles images sont ajoutées, sans configuration supplémentaire nécessaire si les paramètres pour les fichiers sont sinon identiques. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Qualité de la compression des mosaïques </td> 
   <td colname="col2"> <p>Facultatif pour toutes les sources. Pour la compression JPEG, entier compris entre 0 et 100 indiquant comment équilibrer la taille et la qualité de l’image. (La valeur par défaut est zéro.) Un nombre plus élevé produit une meilleure qualité d’image, mais produit des images plus volumineuses et des temps de téléchargement plus longs pour les utilisateurs des outils de données. </p> <p>La compression d’images inférieures à 70 peut entraîner la dégradation de l’image. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compresseur de mosaïque </td> 
   <td colname="col2"> Facultatif pour toutes les sources. Indique la méthode de compression utilisée pour écrire les fichiers de sortie. Les seules méthodes actuellement prises en charge sont RAWRGB (valeur par défaut, sans compression) et JPEG. Utilisez la compression JPEG pour réduire la taille des calques transmis lors de la synchronisation des profils. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Largeur </td> 
   <td colname="col2"> Requis pour les images bitmap brutes non projetées. Largeur de l’image source en pixels. </td> 
  </tr> 
 </tbody> 
</table>

1. Modifiez les paramètres Emplacement de l’image source, Enregistrement d’image temporaire et Ecrire les calques en utilisant le tableau suivant comme guide. Ces paramètres s’appliquent à toutes les sources d’image de terrain que vous définissez dans la section Sources de ce fichier.

   | Paramètre | Description |
   |---|---|
   | Emplacement de l’image source | Obligatoire. Répertoire qui est analysé pour rechercher des images à traduire en couches de terrain. S’il ne s’agit pas d’un chemin d’accès absolu, il est interprété par rapport au répertoire d’installation du serveur de l’outil de données. |
   | Enregistrement d’image temporaire | Facultatif. Nom d’un répertoire utilisé pour l’enregistrement de fichiers temporaires utilisés dans la traduction d’images source vers des couches de terrain. S’il ne s’agit pas d’un chemin d’accès absolu, il est interprété par rapport au répertoire d’installation du serveur de l’outil de données. L’emplacement par défaut est le répertoire Temp. |
   | Ecrire des calques sur | Obligatoire. Répertoire vers lequel les couches de terrain sont produites. Il s’agit généralement du sous-répertoire Maps d’un répertoire de profil, de sorte que la visualisation [!DNL Globe] puisse trouver les calques. |

1. Enregistrez le fichier en cliquant avec le bouton droit **[!UICONTROL (modified)]** dans la partie supérieure de la fenêtre et en cliquant sur **[!UICONTROL Save]**.

1. Pour enregistrer le fichier mis à jour sur l&#39;ordinateur serveur de l&#39;outil de données, dans [!DNL Server Files Manager], cochez la case [!DNL Terrain Images.cfg] dans la colonne [!DNL Temp], puis cliquez sur **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.
