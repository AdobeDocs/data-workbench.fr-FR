---
description: Les dimensions de latence sont construites à partir d’une dimension dénombrable parent, telle que les sessions, et d’une dimension temporelle, telle que Jour.
title: Créer une dimension de latence
uuid: 531d8bf6-a66f-4b02-9d81-05664fb9c988
exl-id: 38b470ef-9409-455b-b2b8-b0391f80b800
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 2%

---

# Créer une dimension de latence{#create-a-latency-dimension}

{{eol}}

Les dimensions de latence sont construites à partir d’une dimension dénombrable parent, telle que les sessions, et d’une dimension temporelle, telle que Jour.

Lorsque vous créez un tableau de latence dans Data Workbench, vous ajoutez automatiquement une dimension de latence au fichier de visualisation (.vw). Vous pouvez modifier la dimension de latence d’un tableau en procédant comme suit.

**Pour modifier une dimension de latence**

1. Ouvrez le tableau de latence que vous avez créé dans un éditeur de texte tel que le Bloc-notes. Il se trouve dans le noeud Utilisateur > `working profile name` > Dossier de travail dans le répertoire d’installation de votre Data Workbench.

   La dimension de latence définie inclut les paramètres affichés dans l’exemple suivant. (La définition de votre dimension de latence peut inclure des paramètres supplémentaires.) Le [!DNL line entity = LatencyDim:] indique le début de la définition de la dimension de latence.

   ```
   entity = LatencyDim:
   Name = string: dimension name
   Level = ref: wdata/model/dim/level
   Clip = ref: wdata/model/dim/clip
   Time = ref: wdata/model/dim/time dimension
   Format = printf_format: 
   format = string: %+0.0f time string
   offset = double: offset
   Time Before = int: time before
   Time After = int: time after
   ```

1. Modifiez les valeurs des paramètres Nom, Niveau, Clip, Heure, Format, Heure avant ou Heure après en utilisant le tableau suivant comme guide :

   <table id="table_13DF30B8B7314F118D0ED5DF9EA70B9B"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Pour ce paramètre... </th> 
      <th colname="col2" class="entry"> Fournissez ces informations... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Nom </p> </td> 
      <td colname="col2"> <p>Facultatif. Le nom de la dimension de latence qui apparaît dans le menu contextuel lorsque vous cliquez avec le bouton droit sur le ou les étiquettes de dimension. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Niveau </p> </td> 
      <td colname="col2"> <p>Dimension dénombrable qui est le parent de la dimension de latence. Par exemple, Session, Visiteur et Page vue. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>clip </p> </td> 
      <td colname="col2"> <p>Dimension dénombrable ayant une relation de type "un à plusieurs" avec le niveau de la dimension de latence. La latence n’est pas calculée au-delà des limites de cette dimension. Par exemple, si vous spécifiez un niveau de page vue et un clip de Session, les latences sont calculées pour les pages vues qui se sont produites au cours de la même session que l’événement. </p> <p>Pour plus d’informations sur les dimensions "un à plusieurs" (simples), voir la section <i>Guide de configuration des jeux de données</i>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Heure </p> </td> 
      <td colname="col2"> <p>Dimension utilisée pour mesurer le temps écoulé pour la dimension de latence. Cette dimension peut être une dimension temporelle, telle que Jour ou Heure, ou une dimension dénombrable, telle que Visiteur, Session ou Page vue. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Format </td> 
      <td colname="col2"> <p>Facultatif. Indique l’aspect de la visualisation de latence en Data Workbench. Dans le paramètre Format , vous pouvez modifier les valeurs suivantes : 
      <ul id="ul_ABF4C17BDE2E4F6C9CBDD933674DE861"> 
         <li id="li_5ED6A7267C81444983AF8507ADC6A5AB">Chaîne d’heure. Unité de temps affichée dans la visualisation de latence, telle qu’un jour ou une semaine. Veillez à modifier la chaîne d’heure lorsque vous modifiez la dimension de temps. </li> 
         <li id="li_E3B517ECE1494221AAE90455CC0AAB42">Décalage. Nombre entier égal au négatif de la valeur pour la valeur Durée avant. Par exemple, si la valeur de l’option Durée avant est 7, le décalage doit être de -7. </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Durée avant </p> </td> 
      <td colname="col2"> <p>Durée maximale (exprimée en unités de la dimension Temps) avant l’événement pour lequel la latence est calculée. Si cette valeur est définie sur 0 ou n’est pas du tout définie, la latence est calculée uniquement pour la direction vers l’avant. </p> <p>Si vous modifiez cette valeur, veillez à modifier la valeur de décalage dans le paramètre Format : Le décalage est le négatif de la valeur pour la valeur Durée avant. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Time After </p> </td> 
      <td colname="col2"> <p>La durée maximale (exprimée en unités de la dimension Durée) après l’événement pour lequel la latence est calculée. </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Enregistrez le [!DNL .vw] dans le dossier User\*working profile name*\Work.

   Voici les paramètres de la dimension de latence par défaut :

   ```
   entity = LatencyDim:
   Name = string: 
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Day
   Time Before = int: 7
   Time After = int: 7
   ```

   Dans la dimension de latence suivante, la latence de chaque événement de session est calculée en heures et l’option Durée avant est définie sur zéro. Par conséquent, la latence est calculée uniquement pour les sessions qui se sont produites dans les 24 heures suivant l’événement défini.

   ```
   entity = LatencyDim:
   Name = string:
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Hour
   Time Before = int: 0
   Time After = int: 24
   ```
