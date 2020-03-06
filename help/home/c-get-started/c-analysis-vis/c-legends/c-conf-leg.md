---
description: Les légendes de confiance vous aident à déterminer la probabilité que les nombres que vous voyez sont dus au hasard et à comprendre les écarts possibles dans les données.
solution: Analytics
title: Légendes de confiance
topic: Data workbench
uuid: 2559ff7c-6060-4fee-b509-9ae0c3912016
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Légendes de confiance{#confidence-legends}

Les légendes de confiance vous aident à déterminer la probabilité que les nombres que vous voyez sont dus au hasard et à comprendre les écarts possibles dans les données.

Même si vous n’effectuez pas d’échantillonnage de données, vous ne pouvez pas extrapoler les chiffres d’une période ou d’un sous-ensemble spécifique à d’autres périodes ou sous-ensembles de temps avec une confiance totale. La légende de confiance vous permet d’explorer la probabilité que les nombres se situent dans une plage particulière.

Si vous considérez les données du monde réel comme une grande expérience, le monde réel implique toujours le hasard, même en travaillant avec des chiffres exacts. Par exemple, le fait de connaître le nombre de personnes qui ont effectué une transaction entre 8 h et 12 h le mardi ne signifie pas que le même nombre sera exact le mardi suivant.

La légende de confiance suivante affiche des détails sur la mesure Conversion, tandis que le tableau suivant fournit des informations supplémentaires sur la signification de chaque point de données.

![](assets/lgd_ConfidenceLegend.png)

<table id="table_387F22C7EF4E4DE9AD810D3D9204676F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Mesure ou formule </p> </td> 
   <td colname="col2"> <p>Nom de la mesure ou expression de mesure pour laquelle vous souhaitez afficher les informations de confiance. Les sélections que vous effectuez dans votre espace de travail sont répercutées dans la légende. Cet exemple présente des détails sur la mesure Conversion. </p> <p>Pour plus d’informations sur les règles de syntaxe permettant de saisir une expression, voir Syntaxe <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f"> du langage de</a>requête. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valeur mesurée </p> </td> 
   <td colname="col2"> <p>Valeur des données réelles collectées. Dans cet exemple, le taux de conversion de la sélection actuelle est de 2,3 %. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Écart type </p> </td> 
   <td colname="col2"> <p>Écart type de la valeur mesurée. Dans cet exemple, l’écart type du taux de conversion pour la sélection actuelle est de 0,1 %. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>La valeur "true" </p> </td> 
   <td colname="col2"> <p>La probabilité que la valeur mesurée soit comprise dans la plage répertoriée pour chaque probabilité. Dans cet exemple, si cette "expérience du monde réel" était répétée encore et encore, vous pourriez être sûr à 90 % que la valeur mesurée serait comprise entre 2,1 % et 2,4 %. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Lors de l’analyse des résultats de tout calcul, vous devez tenir compte des avertissements suivants : >
>* Les chiffres sont des estimations. Si vous répétez les mêmes calculs avec un jeu de données différent, vous obtiendriez un résultat différent. On parle alors de variation aléatoire.
>* Les extrapolations à des probabilités plus élevées dépendent d’une hypothèse de normalité incorrecte pour toutes les mesures. Par conséquent, les valeurs de probabilité à 99 % sont moins fiables que les valeurs de probabilité à 90 %.
>
>
Si vous avez besoin de chiffres plus exacts, vous devriez consulter un expert en statistiques.

## Modification des mesures ou des formules {#section-7f09ff84c3514f26b78d29294e1f03d9}

* Dans la légende de confiance, cliquez dans le **[!UICONTROL Metric or Formula]** champ et saisissez la mesure ou l’expression souhaitée. Pour les règles de syntaxe d’expression, voir Syntaxe [du langage de](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)requête.

## Exporter vers Microsoft Excel {#section-f36e2db7273740b7af278f8a2b79d564}

Pour plus d’informations sur l’exportation de fenêtres, voir [Exportation de données](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)de fenêtre.
