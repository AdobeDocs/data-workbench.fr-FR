---
description: Le menu Arborescence de décision comprend des fonctionnalités permettant de définir le cas d’utilisation positif, les filtres, les options de distribution des feuilles, la matrice de confusion et d’autres options avancées.
title: Options de l’arbre de décision
uuid: 6439c6d4-60ac-4324-b870-b452a63b7ba1
exl-id: e139562d-4613-4159-a858-2a78a2e896dd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 2%

---

# Options de l’arbre de décision{#decision-tree-options}

{{eol}}

Le menu Arborescence de décision comprend des fonctionnalités permettant de définir le cas d’utilisation positif, les filtres, les options de distribution des feuilles, la matrice de confusion et d’autres options avancées.

<table id="table_0CBCCB0856E2469EBE8846B413CAB114"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Bouton Barre d’outils </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Aller </td> 
   <td colname="col2"> Cliquez sur pour exécuter l’algorithme de l’arbre de décision et afficher la visualisation. Ceci est grisé jusqu’à ce qu’il y ait des entrées. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Réinitialiser </td> 
   <td colname="col2"> Efface les entrées et le modèle d’arbre de décision et réinitialise le processus. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enregistrer </td> 
   <td colname="col2"><b>Enregistrement de l’arbre de décision</b>. Vous pouvez enregistrer l’arbre de décision dans différents formats : 
    <ul id="ul_F7C7836C06D64912893113E8EEA05704"> 
     <li id="li_D2D8451A679243F1BC67C3B80CA5F83F">Langage de balisage prédictif (<b>PMML</b>), un format de fichier XML utilisé par les applications pour décrire et échanger des modèles d’arbre de décision. </li> 
     <li id="li_88C4B3E050CA4EFC9B7FA8BD446A9C55"><b>Texte</b> affichant des colonnes et des lignes simples de vrai ou faux, des pourcentages, du nombre de membres et des valeurs d’entrée. </li> 
     <li id="li_3F871B88F3FA41E9B95EFF5A181E3D57">A <b>Dimension</b> avec des branches correspondant aux éléments de résultat prévus. </li> 
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
   <td colname="col1"> Définir un cas positif </td> 
   <td colname="col2"> Définit la sélection actuelle de l’espace de travail comme cas positif du modèle. Efface la casse si aucune sélection n’existe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Définir le filtre de population </td> 
   <td colname="col2"> Définit la sélection actuelle de l’espace de travail comme filtre de population du modèle et sera tracée à partir des visiteurs qui respectent cette condition. La valeur par défaut est "Tout le monde". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Afficher la description de filtre complexe </td> 
   <td colname="col2"> Affiche des descriptions des filtres définis. Cliquez sur pour afficher les scripts de filtrage par cas positif et par filtre de population. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Masquer les noeuds </td> 
   <td colname="col2"> Masque les noeuds avec un faible pourcentage de la population. Cette commande de menu s’affiche uniquement lorsque l’arborescence de décision est affichée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Matrice de confusion </td> 
   <td colname="col2"> <p>Cliquez sur <span class="uicontrol"> Options</span> &gt; <span class="uicontrol"> Matrice de confusion</span> pour afficher les valeurs Précision, Rappel, Précision et F-Score. Plus on se rapproche de 100%, plus le score est élevé. </p> <p>La matrice de confusion donne quatre valeurs d’exactitude du modèle en utilisant une combinaison de valeurs : 
     <ul id="ul_D9D512F5D74B44BDBD27B1912DF4CB02"> 
      <li id="li_28C541DF1CB543FEAF2D13C2F329DB52">Positif réel (AP) </li> 
      <li id="li_56233006A1544D95A72CE096CA55C1E6">Prédit positif (PP) </li> 
      <li id="li_375FB2D6A0A3418A9AD377C9EBB65386">Négatif réel (AN) </li> 
      <li id="li_07A5D23A36BA4D448C25C1414836EB8E">Prédit négatif (PN) </li> 
     </ul> </p> <p>Conseil : Ces chiffres sont obtenus en appliquant le modèle de notation obtenu des données de test de 20 % ignorées et déjà connues comme la vraie réponse. Si le score est supérieur à 50 %, il est prédit comme un cas positif (correspondant au filtre défini). Ensuite, Précision = (TP + TN)/(TP + FP + TN + FN), Rappel = TP / (TP + FN) et Précision = TP / (TP + FP). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Afficher la légende </td> 
   <td colname="col2">Permet d’activer et de désactiver une clé de légende dans l’arbre de décision. <img placement="break" id="image_D5B9415A48C04619955BD96970F720A1" src="assets/decison_tree_legend.png" />Cette commande de menu s’affiche uniquement lorsque l’arborescence de décision est affichée. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Advanced </td> 
   <td colname="col2"> Cliquez pour ouvrir le menu Avancé afin d’utiliser en détail l’arbre de décision. Voir le tableau ci-dessous pour connaître les options de menu. </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_91E4A74BFB224ABD889147324AC2910F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Menu avancé </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Taille du jeu d’entraînement </td> 
   <td colname="col2"> <p>Contrôle la taille du jeu d’entraînement utilisé pour la création du modèle. Les plus grands ensembles prennent plus de temps à s'entraîner, les plus petits ensembles prennent moins de temps. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Normalisation d’entrée </td> 
   <td colname="col2"> <p> Permet à l’utilisateur de spécifier s’il faut utiliser la technique Min-Max ou Score Z pour normaliser les entrées dans le modèle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Facteur de sur-échantillonnage SMOTE </td> 
   <td colname="col2"> Lorsque le cas positif ne se produit pas très souvent (moins de 10 %) dans l’échantillon d’entraînement, l’outil SMOTE est utilisé pour fournir des exemples supplémentaires. Cette option permet à l’utilisateur d’indiquer le nombre d’exemples supplémentaires à créer à l’aide de SMOTE. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seuil de distribution de la classe Leaf </td> 
   <td colname="col2"> Permet de définir le seuil supposé pour une feuille lors du processus de création de l’arborescence. Par défaut, tous les membres d’un noeud doivent être identiques pour être une feuille (avant l’étape d’élagage). </td> 
  </tr> 
 </tbody> 
</table>
