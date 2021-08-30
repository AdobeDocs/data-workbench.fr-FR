---
description: La fonction d’exportation CRS (Customer Record Service) vous permet d’exporter des données de Data Workbench vers les services principaux Adobe Analytics afin de les intégrer à d’autres fonctionnalités d’Analytics, notamment Reports & Analytics.
title: Exportation vers les services principaux Analytics
uuid: 8fd7e8d8-989a-4ad6-bab5-61bfd37b0201
exl-id: 573085e8-2260-4872-be90-a84ad61145bb
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 2%

---

# Exportation vers les services principaux Analytics{#exporting-to-analytics-core-services}

La fonction d’exportation CRS (Customer Record Service) vous permet d’exporter des données de Data Workbench vers les services principaux Adobe Analytics afin de les intégrer à d’autres fonctionnalités d’Analytics, notamment Reports &amp; Analytics.

>[!NOTE]
>
>Pour que la fonction d’exportation CRS fonctionne, l’Analytics ID d’un visiteur doit être basé sur le service d’ID Experience Cloud (ECID). Bien que l’ECID puisse être renseigné dans Data Workbench pour un visiteur, si le client se trouve dans la période de grâce ou que le cookie du visiteur n’a pas été remplacé par l’ECID, l’exportation CRS ne fonctionnera pas pour ce visiteur. Pour plus d’informations, voir [Identification des visiteurs](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-visid.html) et [Période de grâce du service d’ID](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html).

Dans un **Tableau des détails** (clic droit **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]** dans un espace de travail), vous pouvez définir les valeurs d’attribut et les variables requises pour l’intégration avec les Reports &amp; Analytics d’Analytics (à l’aide des services de pipeline Adobe).

1. **Cliquez avec le bouton droit sur l’en-tête du tableau, puis cliquez sur Nouveau service d’enregistrement client.**

   ![](assets/6_4_CRS.png)

1. **Nommez le fichier d’exportation et enregistrez-le.**

   La fenêtre d&#39;édition du fichier d&#39;export s&#39;ouvre.

1. **** **OpenQuery > Configuration CRS**.
1. **Cliquez avec le bouton droit de la souris sur Attributs CRS > Ajouter nouveau.**
1. **** ***Saisissez les*** **paramètres Attributs CRS**.

   Ouvrez la nouvelle entrée et saisissez ou vérifiez les valeurs dans la section *Attributs CRS* du fichier d’exportation :

   ![](assets/6_4_CRS1.png)

   <table id="table_8156A2C66C0E41D381C31F1082CCA479"> 
    <tbody> 
      <tr> 
      <td colname="col1"> <p><b>Nom de l’attribut</b> </p> </td> 
      <td colname="col2">Nom de la variable <i>Attributs du client</i> affichée dans <i>Reports &amp; Analytics</i>. </td> 
      </tr> 
      <tr> 
      <td colname="col1"><b>Type d’attribut</b> </td> 
      <td colname="col2"> <p>Ce paramètre accepte les valeurs de (<i>int</i>, <i>string</i>). </p> <p>Remarque : Si un attribut est <b>not</b> auquel est abonné dans Analytics : <p> 
      <ul id="ul_B77BF6FDA3FB4F1BBF9380C2FD938270"> 
       <li id="li_3D099456AF6B4103B227D841C81AB936">L’attribut sera créé avec tout type d’attribut valide pris en charge par Analytics (pour cette version, il est limité à <i>string</i> et <i>int</i>). </li> 
       <li id="li_EA1DBDB2E6BE49278C6CD6A5503EDC8A">Si un type d’attribut non valide est saisi, vous recevrez une erreur indiquant l’échec de votre abonnement à Analytics. </li> 
      </ul> </p> <p>Si un attribut est <b>déjà</b> abonné à dans Analytics : </p> <p> 
      <ul id="ul_16415B639F1C49A5AE9932C128184171"> 
       <li id="li_83C90D44FE5C4D979DEA786660C7F3EC">Veillez à saisir le type d’attribut approprié pour l’attribut déjà abonné à . </li> 
       <li id="li_02C5024E335C4C59B4F7B0084232CC24">Si vous saisissez un type incorrect pour l’attribut, son comportement dépendra de la gestion des types d’attributs par Analytics. </li> 
      </ul> </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><b>Nom du champ</b> </p> </td> 
      <td colname="col2">Nom de la dimension ou de la mesure à partir de laquelle les valeurs d’attribut sont sélectionnées. <p>Remarque : Le <i><b>nom du champ</b></i> sous <i>Attributs CRS</i> doit être identique aux <b><i>Champs de sortie</i> &gt; <i>Nom du champ</i></b> (qui est renseigné automatiquement en fonction de l’attribut sélectionné). Si le <i>nom du champ</i> n’est pas valide, l’exportation ne s’exécute pas. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Cliquez avec le bouton droit de la souris **[!UICONTROL Report Suite]** > **[!UICONTROL Add New]**.
1. Saisissez les **[!UICONTROL Report Suite ID]**.

   Ouvrez la nouvelle entrée et saisissez ou vérifiez les valeurs dans la section *Suite de rapports* du fichier d’exportation :

   <table id="table_A3279CADB74C441DA2E062E2123CE9D4"> 
    <tbody> 
      <tr> 
      <td colname="col1"><b>Suite de rapports</b> </td> 
      <td colname="col2">Identifiant de la suite de rapports dans <i>Reports &amp; Analytics</i> identifiant les variables <i>Attribut client</i> en cours d’exportation. <p> <p>Remarque : Bien que <i>Reports &amp; Analytics</i> vous permette d’ajouter à plusieurs suites de rapports, Data Workbench 6.4 n’exporte qu’une seule suite de rapports identifiée à <i>index 0</i>. <p>La valeur de la suite de rapports saisie dans ce champ est l’identifiant de la suite de rapports (et non le nom de la suite). </p> </p> </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Saisissez le paramètre Champ ECID .

   **Champ** ECID : Nom de la dimension de votre profil qui représente l’Adobe Experience Cloud ID. Il s’agit d’un champ obligatoire et toute valeur de dimension non valide saisie ne sera pas exportée.

1. (facultatif) Renseignez le paramètre Champ d’identifiant visiteur .

   **Champ d’identifiant visiteur** : Si l’utilisateur souhaite envoyer un autre identifiant personnalisé pour un visiteur dans ses données, c’est là qu’il saisit le nom de la dimension qui représente l’identifiant visiteur personnalisé. Il s’agit d’un champ facultatif qui peut être laissé vide.
