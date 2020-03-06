---
description: Le menu Arborescence de décisions comprend des fonctionnalités permettant de définir le cas d’utilisation positif, les filtres, les options de distribution des feuilles, la matrice de confusion et d’autres options avancées.
title: Options de l'arborescence de décision
uuid: 6439c6d4-60ac-4324-b870-b452a63b7ba1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Options de l&#39;arborescence de décision{#decision-tree-options}

Le menu Arborescence de décisions comprend des fonctionnalités permettant de définir le cas d’utilisation positif, les filtres, les options de distribution des feuilles, la matrice de confusion et d’autres options avancées.

<table id="table_0CBCCB0856E2469EBE8846B413CAB114"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Boutons de la barre d’outils </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Valider </td> 
   <td colname="col2"> Cliquez sur pour exécuter l’algorithme de l’arborescence de décision et afficher la visualisation. Ceci est grisé jusqu’à ce qu’il y ait des entrées. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reset </td> 
   <td colname="col2"> Efface les entrées et le modèle d’arborescence de décision et réinitialise le processus. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enregistrer </td> 
   <td colname="col2"><b>Enregistrez l'arbre</b>de décision. Vous pouvez enregistrer l’arbre de décision dans différents formats : 
    <ul id="ul_F7C7836C06D64912893113E8EEA05704"> 
     <li id="li_D2D8451A679243F1BC67C3B80CA5F83F">Le langage de balisage prédictif (<b>PMML</b>) est un format de fichier XML utilisé par les applications pour décrire et échanger des modèles d’arbre de décision. </li> 
     <li id="li_88C4B3E050CA4EFC9B7FA8BD446A9C55"><b>Texte</b> affichant des colonnes et des lignes simples de valeur true ou false, des pourcentages, du nombre de membres et des valeurs d’entrée. </li> 
     <li id="li_3F871B88F3FA41E9B95EFF5A181E3D57">Une <b>dimension</b> avec des branches correspondant aux éléments de résultat prévus. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Options </td> 
   <td colname="col2"> Voir le tableau ci-dessous pour le menu Options. </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_24D84440D0354C70928E8927624DB255"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Menu Options </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Définir la casse positive </td> 
   <td colname="col2"> Définit la sélection actuelle de l’espace de travail comme cas positif du modèle. Efface le cas si aucune sélection n’existe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Définir le filtre de population </td> 
   <td colname="col2"> Définit la sélection actuelle de l’espace de travail comme filtre de population du modèle et sera effectuée à partir des visiteurs qui remplissent cette condition. La valeur par défaut est "Tout le monde". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Afficher la description du filtre complexe </td> 
   <td colname="col2"> Affiche la description des filtres définis. Cliquez sur pour afficher les scripts de filtrage pour le filtre Cas positif et Population. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Masquer les noeuds </td> 
   <td colname="col2"> Masque les noeuds avec seulement un faible pourcentage de la population. Cette commande de menu s'affiche uniquement lorsque l'arborescence des décisions est affichée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Matrice de confusion </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Options</span> &gt; Matrice <span class="uicontrol"></span> de confusion pour afficher les valeurs Précision, Rappel, Précision et Score F. Plus près de 100 %, plus le score est élevé. </p> <p>La matrice de confusion donne quatre valeurs de précision au modèle à l’aide d’une combinaison de valeurs : 
     <ul id="ul_D9D512F5D74B44BDBD27B1912DF4CB02"> 
      <li id="li_28C541DF1CB543FEAF2D13C2F329DB52">Positif réel (AP) </li> 
      <li id="li_56233006A1544D95A72CE096CA55C1E6">Positif prédit (PP) </li> 
      <li id="li_375FB2D6A0A3418A9AD377C9EBB65386">Négatif réel (AN) </li> 
      <li id="li_07A5D23A36BA4D448C25C1414836EB8E">Négatif prédit (PN) </li> 
     </ul> </p> <p>Conseil :  Ces chiffres sont obtenus en appliquant le modèle de notation résultant des données de test de 20 % retenues et déjà connues comme la réponse vraie. Si le score est supérieur à 50 %, il est prédit comme un cas positif (qui correspond au filtre défini). Puis, Précision = (TP + TN)/(TP + FP + TN + FN), Rappel = TP / (TP + FN) et Précision = TP / (TP + FP). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Afficher la légende </td> 
   <td colname="col2">Permet d’activer ou de désactiver une touche de légende dans l’arborescence des décisions. <img placement="break" id="image_D5B9415A48C04619955BD96970F720A1" src="assets/decison_tree_legend.png" />Cette commande de menu s'affiche uniquement lorsque l'arborescence des décisions est affichée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Advanced </td> 
   <td colname="col2"> Cliquez pour ouvrir le menu Avancé pour une utilisation approfondie de l'arbre de décision. Voir le tableau ci-dessous pour connaître les options de menu. </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_91E4A74BFB224ABD889147324AC2910F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Menu Avancé </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Taille du jeu de formations </td> 
   <td colname="col2"> <p>Contrôle la taille du jeu de formations utilisé pour la création du modèle. Les plus grands ensembles prennent plus de temps à s'entraîner, les plus petits ensembles prennent moins de temps. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Normalisation des entrées </td> 
   <td colname="col2"> <p> Permet à l’utilisateur de spécifier s’il doit utiliser la technique Min-Max ou Score Z pour normaliser les entrées dans le modèle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Facteur de suréchantillonnage de la MOTE </td> 
   <td colname="col2"> Lorsque le cas positif ne se produit pas très souvent (moins de 10 %) dans l’échantillon de formation, SMOTE est utilisé pour fournir des échantillons supplémentaires. Cette option permet à l’utilisateur d’indiquer le nombre d’échantillons supplémentaires à créer à l’aide de SMOTE. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seuil de distribution de classe feuille </td> 
   <td colname="col2"> Permet de définir le seuil supposé pour une feuille pendant le processus de création de l’arborescence. Par défaut, tous les membres d’un noeud doivent être identiques pour qu’il soit une feuille (avant l’étape d’élagage). </td> 
  </tr> 
 </tbody> 
</table>

