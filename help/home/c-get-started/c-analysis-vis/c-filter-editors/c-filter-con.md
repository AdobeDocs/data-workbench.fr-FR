---
description: Informations sur l’utilisation des conditions de filtrage, notamment la création d’un nouveau filtre et l’ajout d’une condition à un nouveau filtre.
title: Utilisation des conditions des filtres
uuid: a75fcb21-be5c-452a-8632-86cd78db15cb
exl-id: 15745b0c-2754-4f8b-acfd-a6bd5886ecf8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 1%

---

# Utilisation des conditions des filtres{#working-with-filter-conditions}

{{eol}}

Informations sur l’utilisation des conditions de filtrage, notamment la création d’un nouveau filtre et l’ajout d’une condition à un nouveau filtre.

## Créer un filtre {#section-70ba51ae625e493fa3ca70b93ffba406}

* Ouvrez un éditeur de filtres dans votre espace de travail en cliquant avec le bouton droit de la souris. **[!UICONTROL Add Visualization]** > **[!UICONTROL Filter Editor]**.

   -ou-

* Si un éditeur de filtres est déjà ouvert et qu’un filtre est chargé, cliquez avec le bouton droit sur le nom du filtre actuel, puis cliquez sur **[!UICONTROL New Blank Filter]**.

## Ajouter une condition à un nouveau filtre {#section-50986db80f1148c489630a8a63fe9f28}

1. Créez un nouveau filtre. Assurez-vous que le filtre de conception est mis en surbrillance (par opposition à Appliquer le filtre), ce qui indique que vous travaillez en mode Filtre de conception.
1. Clic droit dans la zone marquée **[!UICONTROL Right-click to build filter]** et sélectionnez l’une des options suivantes :

   * Pour créer un filtre d’inclusion, cliquez sur **[!UICONTROL Include group with]**.
   * Pour créer un filtre d’exclusion, cliquez sur **[!UICONTROL Exclude group with]**.

1. Sélectionnez le type de condition à ajouter au filtre.

   Le tableau suivant fournit des descriptions des types de conditions de filtre disponibles :

<table id="table_3B35B57FF32349F09E91E8256FF1672A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de condition </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>sélection de l’espace de travail </p> </td> 
   <td colname="col2"> <p>Définit une condition de filtrage basée sur les sélections dans l’espace de travail. Cette option n’est disponible que si l’espace de travail contient une ou plusieurs sélections. </p> <p>Pour afficher plus d’informations sur la sélection, cliquez avec le bouton droit de la souris sur la condition, puis cliquez sur <span class="uicontrol"> Afficher les détails</span>. Une légende s’affiche pour la condition. </p> <p>Si vous effectuez une autre sélection dans l’espace de travail, vous pouvez l’ajouter comme sous-condition de la première sélection. Les sélections sont regroupées sous la forme de ET logiques. Par conséquent, les données incluses ou exclues par la condition doivent satisfaire toutes les sélections de l’espace de travail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>au moins un </p> </td> 
   <td colname="col2">Définit une condition de filtrage basée sur l’existence d’au moins un élément d’une dimension que vous choisissez. Pour modifier la condition, cliquez avec le bouton droit de la souris sur la condition, puis cliquez sur <span class="uicontrol"> Modifier</span> à . Cliquez sur l’une des dimensions disponibles. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>formule </p> </td> 
   <td colname="col2"> <p>Définit une condition de filtrage basée sur la formule que vous avez saisie. Pour que le filtre fonctionne, vous devez utiliser la syntaxe appropriée. </p> <p> <p>Remarque : Pour plus d’informations sur la syntaxe de définition des filtres, voir <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Syntaxe des expressions de filtre</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>valeur de mesure </p> </td> 
   <td colname="col2"> <p>Définit une condition de filtrage basée sur une valeur de mesure que vous spécifiez. </p> <p>Pour définir la condition, procédez comme suit : 
     <ul id="ul_B69D31258A36460E94535709239CD165"> 
      <li id="li_51317A681E654DD7A9D997DF9F2F22BA">Clic droit <span class="uicontrol"> [niveau de sélection]</span> &gt; <span class="uicontrol"> Niveau de changement</span> pour sélectionner le niveau et la mesure dans une liste de dimensions de votre jeu de données. </li> 
      <li id="li_975E56C335824FDCB988344952DE2E9F">Clic droit <span class="uicontrol"> [sélectionner une mesure]</span> &gt; <span class="uicontrol"> Modification de la mesure</span> pour sélectionner la mesure dans une liste de mesures de votre jeu de données. </li> 
      <li id="li_D00B3AF3D8DE472C9D0E9EABBBCAAF61">Cliquez avec le bouton droit de la souris sur moins de et cliquez sur <span class="uicontrol"> Comparaison des modifications</span> pour sélectionner l’une des conditions de comparaison disponibles (inférieur à, plus que, exactement, au moins ou tout au plus). </li> 
      <li id="li_3334CE0A0950448590E5442AB243F46B">Saisissez la valeur souhaitée pour la mesure. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>first/last </p> </td> 
   <td colname="col2"> <p>Définit un filtre qui permet d’inclure ou d’exclure un niveau avec une dimension spécifiée. Par exemple, vous pouvez spécifier un premier/dernier filtre à inclure (ou exclure) : </p> <p>Sessions dont la dernière page vue comporte une page de <span class="filepath"> /home/rts/Nos taux</span>. </p> <p>Pour définir une condition Première/Dernière : 
     <ul id="ul_5AD916DA093844B8AC70127B1EB9BFC8"> 
      <li id="li_AB9FF22ADC8843A79856FED60B9478FA">Choisir <span class="uicontrol"> Inclure le groupe avec</span> ou <span class="uicontrol"> Exclure le groupe avec</span> &gt; <span class="uicontrol"> first/last</span> comme nouvelle condition dans l’éditeur de filtres. </li> 
      <li id="li_92F536FCC2A74DDE97F66C6C45ACC3DC">Clic droit <span class="uicontrol"> [choisir un conteneur]</span> &gt; <span class="uicontrol"> Conteneur de modifications</span> pour sélectionner le conteneur. </li> 
      <li id="li_1E5DBE04ABC74D84B7C0EF6886CDB5DC">Clic droit <span class="uicontrol"> first</span> ou <span class="uicontrol"> last</span> pour spécifier le niveau. </li> 
      <li id="li_8B73EBF5D06E4513B5F0376EB2805D1C">Cliquez avec le bouton droit pour spécifier une dimension, puis entrez une valeur dans le champ disponible. </li> 
      <li id="li_A9E02EF6C6004DDF9B00EB853B6E54EE">Cliquez sur <span class="uicontrol">Appliquer</span>. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Le filtre de cet exemple définit un premier/dernier filtre pour les utilisateurs dont la dernière page vue a été [!DNL /hme/rts/Our Rates]:

![](assets/client-fil2.png)

1. (Facultatif) Pour ajouter d’autres conditions à votre filtre, cliquez avec le bouton droit dans la zone de la fenêtre dans laquelle vous créez votre filtre et sélectionnez le type de filtre (voir Etape 2) et la règle de condition (voir Etape 3).

   >[!NOTE]
   >
   >Plusieurs conditions d’inclusion sont regroupées sous la forme d’OR logiques. Par conséquent, les données incluses par le filtre doivent satisfaire à au moins une des conditions d’inclusion définies. Plusieurs conditions d’exclusion sont également regroupées sous la forme d’OR logiques. Pour être exclues, les données doivent satisfaire à au moins une des conditions d&#39;exclusion.

Le filtre de cet exemple définit un sous-ensemble de données constitué des visionneuses de films (utilisateurs) qui ont évalué de nombreux films mais n’ont attribué aucun score élevé à un film (4 ou 5). Ce filtre (nommé de manière appropriée Très difficile à prioriser) se compose de deux conditions :

* **Une condition de valeur de mesure :** La condition inclut les utilisateurs qui ont évalué au moins 500 films.
* **Une condition de sélection d’espace de travail :** La condition exclut les utilisateurs qui ont donné à un film un score de 4 ou 5. La légende indique que 4 et 5 étaient les éléments sélectionnés dans la dimension Score.

![](assets/vis_FilterEditor_ExampleMovies.png)

## Suppression d’une condition de filtre {#section-3092e0d7ac624885b8fe24616279de13}

>[!NOTE]
>
>Vous ne pouvez supprimer des conditions que lorsque vous travaillez en mode Filtre de conception . Si vous avez appliqué un filtre à votre espace de travail, vous devez cliquer sur Filtre de conception pour revenir au mode Filtre de conception avant de pouvoir supprimer une ou plusieurs des conditions du filtre.

* Cliquez sur le bouton **x** à gauche de la condition pour la supprimer.

## Modification d’une description de condition {#section-5015fd2c88ed4b6a95be7f0d53be2db0}

Vous pouvez ajouter des descriptions à chacune des conditions que vous ajoutez à un filtre. Vous pouvez modifier ou supprimer les descriptions selon vos besoins.

>[!NOTE]
>
>Les descriptions des conditions s’affichent uniquement lorsque vous travaillez en mode Filtre de conception .

* Cliquez avec le bouton droit de la souris sur la condition, puis cliquez sur **[!UICONTROL Edit description]**.

   * Pour ajouter ou modifier une description, saisissez la description dans le champ [!DNL Edit condition description] champ . La description apparaît entre guillemets au-dessus de la condition dans la fenêtre de l’éditeur de filtres.

      ![](assets/vis_FilterEditor_ConditionDescription.png)

* Pour supprimer une description, cliquez sur **[!UICONTROL Remove description]**. La condition reste dans la fenêtre de l&#39;éditeur de filtres.
