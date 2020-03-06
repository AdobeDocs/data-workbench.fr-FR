---
description: Ce fichier fonctionne non seulement comme une feuille de calcul mais aussi comme un enregistrement de vos décisions sur l'expérience.
solution: Insight,Analytics
title: Feuille de calcul de conception d’expérience
topic: Data workbench
uuid: bcb11e39-9cbd-400c-af30-4b1c85e7f218
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Feuille de calcul de conception d’expérience{#experiment-design-spreadsheet}

Ce fichier fonctionne non seulement comme une feuille de calcul mais aussi comme un enregistrement de vos décisions sur l&#39;expérience.

Si vous avez besoin d’aide pour concevoir votre expérience, vous pouvez utiliser la feuille de calcul de conception de l’expérience (nommée VS Controller Experiment Design.xls par défaut) fournie par Adobe.

La feuille de calcul de la conception de l’expérience ne peut fournir des inférences statistiques utiles que lorsque la mesure en question est définie comme un pourcentage de visiteurs qui répondent à certains critères. En d’autres termes, il n’est utile que lors du test d’une hypothèse de mesure basée sur le visiteur.

**Pour concevoir votre expérience à l’aide du fichier de conception de l’expérience**

1. Si vous disposez d’un accès administrateur à vos serveurs Web ou d’applications, accédez au dossier [!DNL Sensor] d’installation sur n’importe quel [!DNL Sensor] ordinateur de votre grappe Web. Si vous ne disposez pas des droits d’administrateur, contactez votre gestionnaire de compte Adobe pour demander le fichier.
1. Ouvrez le fichier VS Controller Experiment Design.xls. (Vous pouvez renommer ce fichier si vous le souhaitez.)

   La feuille de calcul de la page suivante est un exemple de la façon dont vous pourriez remplir la feuille de calcul lorsque vous vous apprêtez à tester l&#39;hypothèse utilisée dans ce guide.

   ![](assets/experimentdesigntop.png)

   ![](assets/experimentdesignmiddle.png)

   ![](assets/experimentdesignbottom.png)

1. Entrez le texte ou les valeurs de tous les champs en bleu de ce fichier, décrits dans le tableau suivant. Les champs calculés sont définis dans le deuxième tableau.

<table id="table_C343F7A4BF3D4E0E9A5E9739EC7C2E10"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dans ce champ... </th> 
   <th colname="col2" class="entry"> Spécifiez les </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Titre de l’expérience </td> 
   <td colname="col2"> Nom descriptif de votre expérience. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Description de l’expérience </td> 
   <td colname="col2"> Description textuelle de l'expérience. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mesure en cours d’étude </td> 
   <td colname="col2"> <p>Nom de la mesure sur laquelle l’expérience est basée. </p> <p>Exemple : Conversion des visiteurs </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Définition de mesure </td> 
   <td colname="col2"> <p>Définition de la mesure sur laquelle l’expérience est basée. </p> <p>Format : Visiteurs[X]/Visiteurs </p> <p>Exemple : Visiteurs <span class="filepath"> [URI='conversionPage.asp']/Visiteurs</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de début prévue </td> 
   <td colname="col2"> Date et heure auxquelles vous voulez que l'expérience commence. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de fin prévue </td> 
   <td colname="col2"> Date et heure auxquelles vous voulez que l'expérience se termine. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sélections applicables </td> 
   <td colname="col2"> (Facultatif) Nom de la dimension et jeu d’éléments ou plage par lesquels vous souhaitez segmenter davantage le jeu de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI d’expérience </td> 
   <td colname="col2"> URI impliqués dans votre hypothèse. Vous définissez les URI actuels pour le groupe de contrôle et les autres URI que vous avez créés ou que vous allez créer pour le ou les groupes de test. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mesures attendues pour les sélections d’applications </td> 
   <td colname="col2"> En-tête des valeurs de mesure attendues pour votre site Web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs moyens par jour </td> 
   <td colname="col2"> Nombre moyen de visiteurs de votre site Web par jour. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conversion des visiteurs </td> 
   <td colname="col2"> Taux moyen de conversion des visiteurs de votre site Web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Expérience Déterminera si le nom de la mesure pour les groupes de test est ... </td> 
   <td colname="col2"> En-tête indiquant comment comparer les valeurs de mesure. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Supérieur À La Valeur Du Groupe De Contrôle ? </td> 
   <td colname="col2"> Définissez ce champ sur True si vous souhaitez pouvoir conclure que la mesure du groupe de tests a augmenté au cours de l’expérience. Définissez ce champ sur False pour réduire le nombre de visiteurs nécessaires pour tirer des conclusions. Adobe recommande de définir cette variable sur True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Inférieur À La Valeur Du Groupe De Contrôle ? </td> 
   <td colname="col2"> Définissez ce champ sur True si vous souhaitez pouvoir conclure que la mesure du groupe de tests a diminué au cours de l’expérience. Adobe recommande de définir cette variable sur True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Par au moins (niveau de détection) </td> 
   <td colname="col2"> Pourcentage selon lequel la mesure du groupe de test doit être supérieure ou inférieure à celle du groupe de contrôle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avec un niveau de confiance d’au moins </td> 
   <td colname="col2"> Niveau de confiance souhaité pour les valeurs du groupe de tests. Le niveau de confiance détermine le nombre de faux positifs pour mesurer la probabilité que l’attente déclarée soit vraie. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> et un niveau de puissance de </td> 
   <td colname="col2"> Niveau de puissance souhaité pour les valeurs du groupe de tests. Le niveau de puissance détermine le nombre de faux négatifs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> % des visiteurs </td> 
   <td colname="col2"> En-tête pour le pourcentage des valeurs de visiteurs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Groupe de tests </td> 
   <td colname="col2"> Pourcentage de visiteurs que vous souhaitez inclure dans le groupe de tests. Vous pouvez lire avec ce nombre jusqu’à ce que la valeur du champ Total (habituellement 100 %) de la section Visiteurs soit égale ou supérieure à la valeur du champ Minimum Visiteurs Obligatoire (Groupes de test+contrôle), qui sont décrits dans le tableau suivant. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Groupe de contrôle </td> 
   <td colname="col2"> Pourcentage de visiteurs que vous souhaitez inclure dans le groupe de contrôle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Autres Design Notes </td> 
   <td colname="col2"> Toute note que vous souhaitez enregistrer pour référence ultérieure. </td> 
  </tr> 
 </tbody> 
</table>

Les champs restants sont calculés en fonction des valeurs que vous avez saisies et sont décrits dans le tableau suivant.

| Champ | Description |
|---|---|
| Mesures attendues pour les sélections d’applications | En-tête des valeurs de mesure attendues pour votre site Web. |
| Visiteurs attendus par période | Ce champ est normalement automatiquement calculé par la feuille de calcul. Elle part du principe que, la plupart des jours, le site Web reçoit beaucoup plus de nouveaux visiteurs que les visiteurs de retour. Dans le cas contraire, le calcul de cette cellule doit être remplacé par le nombre réel de visiteurs attendus au cours de l’expérience. |
| Score Z calculé pour l’erreur de type I | Score Z pour un résultat faux positif. Il s&#39;agit d&#39;un calcul statistique intermédiaire. |
| Score Z calculé pour l’erreur de type II | Score Z pour un résultat faux négatif. Il s&#39;agit d&#39;un calcul statistique intermédiaire. |
| Nombre minimal de visiteurs requis (groupes de test+contrôle) | Nombre minimum de visiteurs requis dans votre expérience pour répondre au niveau de confiance, au niveau de puissance et au score Z spécifiés, exprimé en pourcentage de la valeur dans le champ Visiteurs attendus par période. |
| Nombre minimal de visiteurs requis (groupes de test+contrôle) | Nombre minimum de visiteurs requis dans votre expérience pour répondre au niveau de confiance, au niveau de puissance et au score Z spécifiés. Cette valeur doit être inférieure ou égale à la valeur du champ Total (100 % en général) de la section Visiteurs. |
| Durée d’expérience minimale (jours) | Nombre minimum de jours nécessaires pour exécuter l’expérience afin d’atteindre le niveau de confiance, le niveau d’alimentation et le score Z que vous avez spécifiés. Ce nombre calculé est sujet aux mêmes problèmes que ceux décrits dans le champ Visiteurs attendus par période. Dans le cas d’un site Web qui compte de nombreux visiteurs récurrents, le champ Durée d’expérience minimale (jours) correspond au nombre de jours attendu nécessaire pour afficher un nombre de visiteurs uniques égal à la valeur du champ Nombre minimum de visiteurs requis. |
| Visiteurs | En-tête des valeurs des visiteurs. |
| Groupe de tests | Nombre de visiteurs requis dans le groupe de tests. |
| Groupe de contrôle | Nombre de visiteurs requis dans le groupe de contrôle. |
| Total (généralement 100 %) | Nombre total de visiteurs nécessaires pour l’expérience. Cette valeur doit être égale ou supérieure à la valeur du champ Minimum Visiteurs Required (Groupes de test+contrôle). |
| Exactitude du groupe de tests (au niveau de confiance de Target) | Pourcentage indiquant qu’il y a une chance égale au niveau de confiance spécifié que la valeur mesurée de la mesure calculée pour le groupe de test sera comprise dans ce pourcentage de sa valeur réelle. |
| Précision du groupe de contrôle (au niveau de fiabilité de Target) | Pourcentage indiquant qu’il y a une chance égale au niveau de confiance spécifié que la valeur mesurée de la mesure calculée pour le groupe de contrôle se trouve dans ce pourcentage de sa valeur réelle. |
| Score Z (avec précision de la cible) | Nombre d’écarts types entre une valeur donnée et la moyenne d’essai. |
| Niveau de confiance réel (à l’intervalle cible) | Niveau de confiance atteint pour l&#39;expérience. Le degré de confiance mesure la probabilité que l’attente déclarée soit vraie. |
| Intervalle réel (au niveau de confiance cible) | Intervalle de confiance atteint pour l’expérience, qui fournit une plage estimée de valeurs susceptible d’inclure un paramètre de population inconnu. Cette plage est calculée à partir d’un ensemble donné de données d’exemple. |

Vous devez examiner la valeur du champ Minimum Visiteurs Required (Groupes de test+contrôle). . .

![](assets/Experiment_Design_Min_Visitors.png)

et comparez-la à la valeur du champ Total dans la [!DNL Visitors] colonne.

![](assets/Experiment_Design_Total_Visitors.png)

Pour que votre expérience soit statistiquement valide, la valeur du champ Total (habituellement 100 %) doit être égale ou supérieure à la valeur du champ Minimum Visiteurs Required (Test+Groupes de contrôle).

Compte tenu des entrées fournies, l’exemple de feuille de calcul montre que 10 475 visiteurs doivent participer à cette expérience pour atteindre le taux de confiance de 95 % saisi (le degré de confiance suggéré minimal pour toute expérience contrôlée, bien que vous puissiez augmenter ce nombre). L&#39;expérience, telle qu&#39;elle est actuellement conçue, compte 30 000 visiteurs, soit bien plus que le nombre minimum de visiteurs requis.

Si vous conservez le même nombre de jours, vous pouvez augmenter le niveau de confiance tant que le nombre total de visiteurs continue à atteindre ou à dépasser le minimum requis.

1. Enregistrez le fichier pour vos enregistrements, puis utilisez les informations du fichier pour configurer l’expérience à l’aide de la feuille de calcul de configuration de l’expérience. Pour plus d’informations sur cette feuille de calcul, voir [Configuration et déploiement de l’expérience](../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).
