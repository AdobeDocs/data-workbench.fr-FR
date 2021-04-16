---
description: Ce fichier fonctionne non seulement comme une feuille de calcul mais aussi comme un enregistrement de vos décisions concernant l'expérience.
solution: Analytics,Analytics
title: Feuille de calcul de conception des expériences
uuid: bcb11e39-9cbd-400c-af30-4b1c85e7f218
exl-id: 554790ab-1182-4481-87b0-e768ea769ddf
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 0%

---

# Feuille de calcul de conception des expériences{#experiment-design-spreadsheet}

Ce fichier fonctionne non seulement comme une feuille de calcul mais aussi comme un enregistrement de vos décisions concernant l&#39;expérience.

Si vous avez besoin d&#39;aide pour concevoir votre expérience, vous pouvez utiliser la feuille de calcul de conception de l&#39;expérience (nommée VS Controller Experiment Design.xls par défaut) fournie par Adobe.

La feuille de calcul de la conception de l&#39;expérience ne peut fournir des inférences statistiques utiles que lorsque la mesure en question est définie en tant que pourcentage de visiteurs qui répondent à certains critères. En d’autres termes, il n’est utile que lors du test d’une hypothèse de mesures basée sur un visiteur.

**Pour concevoir votre expérience à l&#39;aide du fichier de conception de l&#39;expérience**

1. Si vous disposez d’un accès administrateur à vos serveurs Web ou d’applications, accédez au dossier d’installation [!DNL Sensor] sur n’importe quel ordinateur [!DNL Sensor] de votre grappe Web. Si vous n’avez pas d’accès administrateur, contactez votre gestionnaire de compte d’Adobe pour demander le fichier.
1. Ouvrez le fichier VS Controller Experiment Design.xls. (Si vous le souhaitez, vous pouvez renommer ce fichier.)

   La feuille de calcul de la page suivante est un exemple de la façon dont vous pourriez remplir la feuille de calcul lorsque vous vous apprêteriez à tester l&#39;hypothèse d&#39;exemple utilisée dans ce guide.

   ![](assets/experimentdesigntop.png)

   ![](assets/experimentdesignmiddle.png)

   ![](assets/experimentdesignbottom.png)

1. Entrez le texte ou les valeurs de tous les champs en bleu de ce fichier, qui sont décrits dans le tableau suivant. Les champs calculés sont définis dans le deuxième tableau.

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
   <td colname="col1"> Description de l'expérience </td> 
   <td colname="col2"> Description textuelle de l'expérience. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mesure en cours d’étude </td> 
   <td colname="col2"> <p>Nom de la mesure sur laquelle repose l’expérience. </p> <p>Exemple : Conversion de visiteur </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Définition de mesure </td> 
   <td colname="col2"> <p>Définition de la mesure sur laquelle l’expérience est basée. </p> <p>Format : Visiteur[X]/Visiteur </p> <p>Exemple : <span class="filepath"> Visiteurs[URI='conversionpage.asp']/Visiteurs</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Début prévu </td> 
   <td colname="col2"> Date et heure auxquelles vous voulez que l'expérience commence. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de fin prévue </td> 
   <td colname="col2"> Date et heure auxquelles vous voulez que l'expérience se termine. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sélections applicables </td> 
   <td colname="col2"> (Facultatif) Nom de dimension et jeu d’éléments ou plage selon laquelle vous souhaitez segmenter davantage le jeu de données. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI d’expérience </td> 
   <td colname="col2"> URI impliqués dans votre hypothèse. Vous définissez les URI actuels pour la Population témoin et les autres URI que vous avez créés ou que vous allez créer pour le ou les groupes de test. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mesures prévues pour les sélections d’applications </td> 
   <td colname="col2"> En-tête des valeurs de mesure attendues pour votre site Web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visiteurs moyens par jour </td> 
   <td colname="col2"> Nombre moyen de visiteurs sur votre site Web par jour. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conversion de visiteur </td> 
   <td colname="col2"> Taux de conversion visiteur moyen pour votre site Web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Expérience Déterminera si le nom de la mesure pour les groupes de test est ... </td> 
   <td colname="col2"> En-tête permettant de comparer les valeurs des mesures. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Supérieur à la valeur de la Population témoin ? </td> 
   <td colname="col2"> Définissez ce champ sur True si vous souhaitez pouvoir conclure que la mesure du groupe de tests a augmenté au cours de l’expérience. Définissez ce champ sur False pour réduire le nombre de visiteurs nécessaires pour tirer des conclusions. Adobe recommande de lui affecter la valeur True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Inférieur À La Valeur De La Population témoin ? </td> 
   <td colname="col2"> Définissez ce champ sur True si vous souhaitez pouvoir conclure que la mesure du groupe de tests a diminué pendant l’expérience. Adobe recommande de lui affecter la valeur True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Par au moins (niveau de détection) </td> 
   <td colname="col2"> Pourcentage selon lequel la mesure du groupe de test doit être supérieure ou inférieure à celle de la Population témoin. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Avec un niveau de confiance d’au moins </td> 
   <td colname="col2"> Niveau de confiance souhaité pour les valeurs du groupe de tests. Le degré de confiance détermine le nombre de faux positifs pour mesurer la probabilité que l’attente déclarée soit vraie. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> et un niveau de puissance de </td> 
   <td colname="col2"> Niveau de puissance souhaité pour les valeurs du groupe de tests. Le niveau d'alimentation détermine le nombre de faux négatifs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> % de Visiteur </td> 
   <td colname="col2"> En-tête pour le pourcentage de valeurs visiteuses. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Groupe de tests </td> 
   <td colname="col2"> Pourcentage de visiteurs que vous souhaitez inclure dans le groupe de tests. Vous pouvez lire avec ce nombre jusqu’à ce que la valeur du champ Total (habituellement 100 %) de la section Visiteur soit égale ou supérieure à la valeur du champ Minimum Visiteurs obligatoires (Test+Populations témoins), tous deux décrits dans le tableau suivant. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Population témoin </td> 
   <td colname="col2"> Pourcentage de visiteurs que vous souhaitez inclure dans la Population témoin. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Autres notes de conception </td> 
   <td colname="col2"> Toute note que vous souhaitez enregistrer pour référence ultérieure. </td> 
  </tr> 
 </tbody> 
</table>

Les champs restants sont calculés en fonction des valeurs que vous avez saisies et sont décrits dans le tableau suivant.

| Champ | Description |
|---|---|
| Mesures prévues pour les sélections d’applications | En-tête des valeurs de mesure attendues pour votre site Web. |
| Visiteurs attendus par période | Ce champ est normalement automatiquement calculé par la feuille de calcul. Il repose sur l&#39;hypothèse que, la plupart des jours, le site Web reçoit beaucoup plus de nouveaux visiteurs que de visiteurs de retour. Si ce n’est pas le cas, le calcul de cette cellule doit être remplacé par le nombre réel de visiteurs attendus au cours de l’expérience. |
| Score Z calculé pour l’erreur de type I | Score Z pour un résultat faux positif. Il s&#39;agit d&#39;un calcul statistique intermédiaire. |
| Score Z calculé pour l’erreur de type II | Score Z pour un résultat faux négatif. Il s&#39;agit d&#39;un calcul statistique intermédiaire. |
| Visiteurs minimum requis (test+Populations témoins) | Nombre minimum de visiteurs requis dans votre expérience pour répondre à votre niveau de confiance, à votre niveau d’alimentation et à votre score Z spécifiés, exprimé en pourcentage de la valeur du champ Visiteurs attendus par période. |
| Visiteurs minimum requis (test+Populations témoins) | Nombre minimum de visiteurs requis dans votre expérience pour satisfaire à votre niveau de confiance, à votre niveau de puissance et à votre score Z spécifiés. Cette valeur doit être inférieure ou égale à la valeur du champ Total (habituellement 100 %) de la section Visiteurs. |
| Durée d’expérience minimale (jours) | Nombre minimum de jours nécessaires à l&#39;exécution de l&#39;expérience pour atteindre le niveau de confiance, le niveau d&#39;alimentation et le score Z que vous avez spécifiés. Ce nombre calculé est sujet aux mêmes problèmes que ceux qui sont abordés dans le champ Visiteurs attendus par période. Dans le cas d’un site Web qui compte de nombreux visiteurs de retour, le champ Durée d’expérience minimale (jours) correspond au nombre de jours attendu nécessaire pour afficher un nombre de visiteurs uniques égal à la valeur du champ Visiteurs minimaux requis. |
| Visiteurs | En-tête des valeurs visiteuses. |
| Groupe de tests | Nombre de visiteurs requis dans le groupe de test. |
| Population témoin | Nombre de visiteurs nécessaires dans la Population témoin. |
| Total (généralement 100 %) | Nombre total de visiteurs nécessaires pour l&#39;expérience. Cette valeur doit être égale ou supérieure à la valeur du champ Minimum Visiteurs Required (Test+Populations témoins). |
| Vérifier la précision du groupe (au niveau de fiabilité de la Cible) | Pourcentage indiquant qu’il y a une chance égale au degré de confiance spécifié que la valeur mesurée de la mesure calculée pour le groupe de test sera comprise dans ce pourcentage de sa valeur réelle. |
| Précision de la Population témoin (au niveau de fiabilité de la Cible) | Pourcentage indiquant qu’il y a une chance égale au degré de confiance spécifié que la valeur mesurée de la mesure calculée pour la Population témoin sera comprise dans ce pourcentage de sa valeur réelle. |
| Score Z (à la précision de la Cible) | Nombre d&#39;écarts types par rapport à la moyenne d&#39;essai. |
| Niveau de confiance réel (à l’intervalle de Cible) | Niveau de confiance atteint pour l&#39;expérience. Le degré de confiance mesure la probabilité que l’attente déclarée soit vraie. |
| Intervalle réel (au niveau de confiance de la Cible) | Intervalle de confiance atteint pour l&#39;expérience, qui fournit une plage estimée de valeurs qui est susceptible d&#39;inclure un paramètre de population inconnu. Cette plage est calculée à partir d’un ensemble donné de données d’exemple. |

Vous devez examiner la valeur du champ Minimum Visiteurs Required (Test+Populations témoins). . .

![](assets/Experiment_Design_Min_Visitors.png)

et comparez-la à la valeur du champ Total dans la colonne [!DNL Visitors].

![](assets/Experiment_Design_Total_Visitors.png)

Pour que votre expérience soit statistiquement valide, la valeur du champ Total (habituellement 100 %) doit être égale ou supérieure à la valeur du champ Visiteurs minimaux requis (Test+Populations témoins).

Compte tenu des entrées fournies, l&#39;exemple de feuille de calcul montre que 10 475 visiteurs doivent participer à cette expérience pour atteindre le taux de confiance de 95 % saisi (qui est le degré de confiance minimum suggéré pour toute expérience contrôlée, bien que vous puissiez augmenter ce nombre). L&#39;expérience telle qu&#39;elle est actuellement conçue comprend 30 000 visiteurs, ce qui est bien supérieur au nombre minimum de visiteurs requis.

Si vous conservez le même nombre de jours, vous pouvez augmenter le niveau de confiance tant que le nombre total de visiteurs continue à respecter ou à dépasser le minimum requis.

1. Enregistrez le fichier pour vos enregistrements, puis utilisez les informations du fichier pour configurer l&#39;expérience à l&#39;aide de la feuille de calcul de configuration de l&#39;expérience. Pour plus d’informations sur cette feuille de calcul, voir [Configuration et déploiement de l’expérience](../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).
