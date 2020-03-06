---
description: Vous définissez de nouvelles mesures (appelées mesures dérivées) et modifiez les définitions de mesures existantes à l’aide de l’éditeur de mesures.
solution: Analytics
title: Utilisation des mesures dérivées
topic: Data workbench
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Utilisation des mesures dérivées{#work-with-derived-metrics}

Vous définissez de nouvelles mesures (appelées mesures dérivées) et modifiez les définitions de mesures existantes à l’aide de l’éditeur de mesures.

Pour plus d’informations sur les mesures que celles fournies dans cette section et dans la syntaxe [du langage de](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)requête, consultez le Guide *des* mesures, des dimensions et des filtres.

## Création d’une mesure dérivée {#section-d57b98bf0a9940daba4920ff7efc808d}

Vous utilisez un [!DNL Metric Editor] pour définir une nouvelle mesure par nom, formule et format, qui est enregistrée dans le dossier User\*profile_name*\Metrics pour une utilisation ultérieure.

1. Ouvrez une nouvelle [!DNL Metric Editor] à l’aide de l’option **[!UICONTROL Admin]** > **[!UICONTROL Profile]** ou en cliquant avec le bouton droit sur la **[!UICONTROL User]** colonne du dossier dans lequel vous souhaitez créer la mesure et en cliquant sur **[!UICONTROL Create]** > **[!UICONTROL New Metric]**.

   Un [!DNL Metric Editor] écran s’affiche.

1. Dans le paramètre Nom, saisissez le nom de la nouvelle mesure.

   Notez que les espaces ( ) sont autorisés, contrairement aux traits de soulignement (_). En outre, vous ne pouvez pas utiliser les symboles suivants :

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. Dans le paramètre Formule, saisissez une expression pour la nouvelle mesure. Notez que les filtres doivent être définis entre crochets [ ] dans l’expression.

   Pour plus d’informations sur les règles de syntaxe d’expression de mesure, voir [Syntaxe pour les expressions](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66)de mesure.

   Le tableau suivant fournit des exemples d’expressions pour les mesures étendues.

   <table id="table_ED77997FC08F492490DCAC3C4153781C"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Nom de la mesure étendue </th> 
      <th colname="col2" class="entry"> Expression </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Pourcentage des premières sessions </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Sessions [Session_Number="1"]/Sessions</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Première session de conversion </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Conversion [Session_Number="1"]</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Valeur moyenne par visiteur </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Valeur/Visiteurs</span> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   >[!NOTE]
   >
   >Lorsqu’une expression appropriée est saisie, la ligne d’aperçu affiche la valeur de la nouvelle mesure. En cas d’erreur dans l’expression, la ligne d’aperçu affiche un message d’erreur.

1. Cliquez avec le bouton droit **[!UICONTROL (New)]** de la souris, puis cliquez **[!UICONTROL Save]**.

   Lorsque vous enregistrez la mesure, un fichier représentant la nouvelle mesure est créé sur votre ordinateur dans le répertoire d’installation des outils de données \User\*nom du profil*\Metrics.

   ![](assets/vis_MetricEditor_NewAndEditing.png)

Vous pouvez désormais utiliser la nouvelle mesure dans l’ensemble du profil actuel en la sélectionnant comme vous le feriez pour toute mesure intégrée. Pour modifier l’ordre d’affichage des mesures dans le menu des mesures, voir [Personnalisation des menus à l’aide de fichiers](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.

Si vous souhaitez que tous les utilisateurs du profil utilisent la mesure que vous avez créée, vous devez la publier dans le profil de travail à l’aide de la [!DNL Profile Manager]. Voir [Publication de fichiers dans votre profil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)de travail.

## Modification de mesures dérivées {#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. Dans la colonne [!DNL Profile Manager] ou [!DNL Metrics Manager], dans la colonne Nom *du* profil, cliquez avec le bouton droit de la souris sur la coche correspondant au fichier de mesure à modifier, puis cliquez sur **[!UICONTROL Make Local]**.
1. Cliquez avec le bouton droit de la souris sur la coche du fichier de mesure dans la [!DNL User] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   >[!NOTE]
   >
   >Vous pouvez également ouvrir une [!DNL Metric Editor] mesure en cliquant avec le bouton droit de la souris sur une zone liée aux mesures dans une visualisation pour afficher le menu des mesures. Pour plus d’informations, voir [Utilisation des menus](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac)de mesure et de dimension.

1. Dans la section [!DNL Metric Editor], modifiez et enregistrez la définition de mesure selon les besoins à l’aide des étapes 2 à 4 de [Création de nouvelles mesures](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d)dérivées.

   Si vous souhaitez que tous les utilisateurs du profil utilisent la mesure que vous avez modifiée, vous devez la publier dans le profil de travail à l’aide de la [!DNL Profile Manager]. Voir [Publication de fichiers dans votre profil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)de travail.

