---
description: Vous définissez de nouvelles mesures (appelées mesures dérivées) et modifiez les définitions de mesures existantes à l’aide de l’éditeur de mesures.
title: Utilisation de mesures dérivées
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
exl-id: 83467c64-4b9a-44ab-91a2-202c76c89979
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# Utilisation de mesures dérivées{#work-with-derived-metrics}

{{eol}}

Vous définissez de nouvelles mesures (appelées mesures dérivées) et modifiez les définitions de mesures existantes à l’aide de l’éditeur de mesures.

Pour plus d’informations sur les mesures, reportez-vous à cette section et à la section [Syntaxe du langage de requête](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f), reportez-vous à la section *Guide des mesures, Dimensions et filtres*.

## Création d’une mesure dérivée {#section-d57b98bf0a9940daba4920ff7efc808d}

Vous utilisez une [!DNL Metric Editor] pour définir une nouvelle mesure par nom, formule et format, qui est enregistrée dans le dossier User\*profile_name*\Metrics en vue d’une utilisation ultérieure.

1. Ouvrez une nouvelle [!DNL Metric Editor] en utilisant la variable **[!UICONTROL Admin]** > **[!UICONTROL Profile]** ou en cliquant avec le bouton droit de la souris sur l’option **[!UICONTROL User]** pour le dossier dans lequel vous souhaitez créer la mesure et en cliquant sur **[!UICONTROL Create]** > **[!UICONTROL New Metric]**.

   A [!DNL Metric Editor] s’affiche.

1. Dans le paramètre Nom, saisissez le nom de la nouvelle mesure.

   Notez que les espaces ( ) sont autorisés, contrairement aux traits de soulignement (_). En outre, vous ne pouvez pas utiliser les symboles suivants :

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. Dans le paramètre Formule , saisissez une expression pour la nouvelle mesure. Notez que les filtres doivent être définis entre crochets. [ ] dans l’expression .

   Pour obtenir des règles de syntaxe d’expression de mesure supplémentaires, reportez-vous à la section [Syntaxe des expressions de mesure](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66).

   Le tableau suivant fournit des exemples d’expressions pour les mesures étendues.

   <table id="table_ED77997FC08F492490DCAC3C4153781C"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Nom de mesure étendue </th> 
      <th colname="col2" class="entry"> Expression </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Pourcentage des premières sessions </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Sessions [Session_Number="1"]/Sessions</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Premières sessions de conversion </p> </td> 
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

1. Clic droit **[!UICONTROL (New)]** et cliquez sur **[!UICONTROL Save]**.

   Lorsque vous enregistrez la mesure, un fichier représentant la nouvelle mesure est créé sur votre ordinateur dans le dossier Répertoire d’installation du Data Workbench \User\*nom du profil*\Mesures.

   ![](assets/vis_MetricEditor_NewAndEditing.png)

Vous pouvez désormais utiliser la nouvelle mesure dans l’ensemble du profil actuel en la sélectionnant comme vous le feriez pour toute mesure intégrée. Pour modifier l’ordre dans lequel vos mesures apparaissent dans le menu des mesures, voir [Personnalisation des menus à l’aide des fichiers Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

Si vous souhaitez que tous les utilisateurs du profil utilisent la mesure que vous avez créée, vous devez la publier sur le profil de travail à l’aide de la variable [!DNL Profile Manager]. Voir [Publication de fichiers dans votre profil de travail](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

## Modification d’une mesure dérivée {#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. Dans le [!DNL Profile Manager] ou [!DNL Metrics Manager], dans la variable *nom du profil* , cliquez avec le bouton droit de la souris sur la coche du fichier de mesure à modifier, puis cliquez sur **[!UICONTROL Make Local]**.
1. Cliquez avec le bouton droit de la souris sur la coche du fichier de mesure dans le [!DNL User] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   >[!NOTE]
   >
   >Vous pouvez également ouvrir une [!DNL Metric Editor] en cliquant avec le bouton droit de la souris sur une zone liée aux mesures dans une visualisation pour afficher le menu des mesures. Pour plus d’informations, voir [Utilisation des menus de mesure et de Dimension](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac).

1. Dans le [!DNL Metric Editor], modifiez et enregistrez la définition de mesure selon les besoins à l’aide des étapes 2 à 4 de la section [Création de mesures dérivées](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d).

   Si vous souhaitez que tous les utilisateurs du profil utilisent la mesure que vous avez modifiée, vous devez la publier sur le profil de travail à l’aide de la variable [!DNL Profile Manager]. Voir [Publication de fichiers dans votre profil de travail](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
