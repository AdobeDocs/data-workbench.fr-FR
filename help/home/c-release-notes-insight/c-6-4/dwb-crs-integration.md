---
description: La fonction d’exportation CRS (Customer Record Service) vous permet d’exporter les données des outils de données vers les services principaux d’Adobe Analytics afin de les intégrer aux fonctionnalités d’autres analyses, notamment les rapports et analyses.
title: Exportation vers Analytics Core Services
uuid: 8fd7e8d8-989a-4ad6-bab5-61bfd37b0201
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exportation vers Analytics Core Services{#exporting-to-analytics-core-services}

La fonction d’exportation CRS (Customer Record Service) vous permet d’exporter les données des outils de données vers les services principaux d’Adobe Analytics afin de les intégrer aux fonctionnalités d’autres analyses, notamment les rapports et analyses.

>[!NOTE]
>
>Pour que la fonction d’exportation CRS fonctionne, l’Analytics ID d’un visiteur doit être basé sur le service d’ID d’expérience (ECID). Bien que l’ECID puisse être renseigné dans les Outils de données pour un visiteur, si le client est dans la période de grâce ou si le cookie du visiteur n’a pas été remplacé par l’ECID, l’exportation CRS ne fonctionnera pas pour ce visiteur. Pour plus d’informations, voir [Identification des visiteurs](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-visid.html) et période [de grâce du service d’](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/grace-period.html)ID.

Dans un tableau **** détaillé (cliquez avec le bouton droit **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]** dans un espace de travail), vous pouvez définir les valeurs d’attribut et les variables requises pour l’intégration aux rapports et analyses d’Analytics (à l’aide d’Adobe Pipeline Services).

1. **Cliquez avec le bouton droit sur l’en-tête du tableau et cliquez sur Nouveau service d’enregistrement des clients.**

   ![](assets/6_4_CRS.png)

1. **Nommez le fichier d’exportation et enregistrez-le.**

   La fenêtre de modification du fichier d’exportation s’ouvre.

1. **Ouvrez** **Requête > Configuration** CRS.
1. **Cliquez avec le bouton droit de la souris sur Attributs CRS > Ajouter nouveau.**
1. **Entrez** les attributs ****** CRS ****.

   Ouvrez la nouvelle entrée et saisissez ou vérifiez les valeurs dans la section Attributs ** CRS du fichier d’exportation :

   ![](assets/6_4_CRS1.png)

   <table id="table_8156A2C66C0E41D381C31F1082CCA479"> 
    <tbody> 
      <tr> 
      <td colname="col1"> <p><b>Nom d’attribut</b> </p> </td> 
      <td colname="col2">Nom de la variable Attributs <i>du</i> client affichée dans les <i>rapports et analyses</i>. </td> 
      </tr> 
      <tr> 
      <td colname="col1"><b>Type d’attribut</b> </td> 
      <td colname="col2"> <p>Ce paramètre accepte les valeurs de (<i>int</i>, <i>string</i>). </p> <p>Remarque : Si un attribut n’est <b>pas</b> abonné dans Analytics : <p> 
      <ul id="ul_B77BF6FDA3FB4F1BBF9380C2FD938270"> 
       <li id="li_3D099456AF6B4103B227D841C81AB936">L’attribut sera créé avec tout type d’attribut valide pris en charge par Analytics (pour cette version, il est limité à <i>la chaîne</i> et à <i>int</i>uniquement). </li> 
       <li id="li_EA1DBDB2E6BE49278C6CD6A5503EDC8A">Si un type d’attribut non valide est saisi, une erreur s’affiche indiquant l’échec de l’abonnement à Analytics. </li> 
      </ul> </p> <p>Si un attribut est <b>déjà</b> abonné dans Analytics : </p> <p> 
      <ul id="ul_16415B639F1C49A5AE9932C128184171"> 
       <li id="li_83C90D44FE5C4D979DEA786660C7F3EC">Veillez à entrer le type d’attribut approprié pour l’attribut déjà abonné à. </li> 
       <li id="li_02C5024E335C4C59B4F7B0084232CC24">Si vous saisissez un type incorrect pour l’attribut, son comportement dépend de la gestion des types d’attributs par Analytics. </li> 
      </ul> </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><b>Nom du champ</b> </p> </td> 
      <td colname="col2">Nom de la dimension ou de la mesure à partir de laquelle les valeurs d’attribut sont sélectionnées. <p>Remarque : Le nom <i><b>du</b></i> champ sous Attributs <i></i> CRS doit être identique à celui des champs <b><i>de</i> sortie &gt; Nom du <i>champ (renseigné automatiquement en fonction de l’attribut sélectionné). </i></b> Si le nom <i>du</i> champ n’est pas valide, l’exportation ne s’exécute pas. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Cliquez avec le bouton droit **[!UICONTROL Report Suite]** > **[!UICONTROL Add New]**.
1. Saisissez les **[!UICONTROL Report Suite ID]**.

   Ouvrez la nouvelle entrée et saisissez ou vérifiez les valeurs dans la section Suite *de* rapports du fichier d’exportation :

   <table id="table_A3279CADB74C441DA2E062E2123CE9D4"> 
    <tbody> 
      <tr> 
      <td colname="col1"><b>Suite de rapports</b> </td> 
      <td colname="col2">ID de la suite de rapports dans les <i>rapports et analyses</i> identifiant les variables d’attribut <i></i> client en cours d’exportation. <p> <p>Remarque : Bien que les <i>rapports et analyses</i> vous permettent d’ajouter des données à plusieurs suites de rapports, les outils de données version 6.4 exportent uniquement une seule suite de rapports identifiée à l’ <i>index 0</i>. <p>La valeur de la suite de rapports saisie dans ce champ est l’identifiant de la suite de rapports (et non le nom de la suite). </p> </p> </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Saisissez le paramètre Champ ECID.

   **Champ** ECID : Nom de la dimension de votre profil qui représente l’Adobe Experience Cloud ID. Il s’agit d’un champ obligatoire et toute valeur de dimension non valide saisie n’est pas exportée.

1. (Facultatif) Renseignez le paramètre Champ d’identifiant visiteur.

   **Champ** Identifiant visiteur : Si l’utilisateur souhaite envoyer un autre identifiant personnalisé pour un visiteur dans ses données, c’est là qu’il entre le nom de la dimension qui représente l’identifiant visiteur personnalisé. Il s’agit d’un champ facultatif qui peut être laissé vide.
