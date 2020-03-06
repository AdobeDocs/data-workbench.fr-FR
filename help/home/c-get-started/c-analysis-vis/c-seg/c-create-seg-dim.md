---
description: Pour créer une dimension de segment, vous commencez par effectuer une sélection dans un espace de travail, puis vous ajoutez le segment à une visualisation.
solution: Analytics
title: Création de dimensions de segment
topic: Data workbench
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Création de dimensions de segment{#create-a-segment-dimensions}

Pour créer une dimension de segment, vous commencez par effectuer une sélection dans un espace de travail, puis vous ajoutez le segment à une visualisation.

**Pour créer une dimension de segment**

1. Ajoutez une visualisation des segments à l’espace de travail. Par exemple :

   ![](assets/vis_Segment.png)

1. Ajoutez des visualisations à votre espace de travail que vous souhaitez utiliser pour définir votre segment, puis effectuez les sélections souhaitées pour définir votre segment.
1. Dans la visualisation des segments, cliquez avec le bouton droit de la souris sur l’étiquette du segment après lequel vous souhaitez ajouter le nouveau segment, puis cliquez sur **[!UICONTROL Add Segment]**.

   >[!NOTE]
   >
   >Pour créer un nouveau premier segment, cliquez avec le bouton droit de la souris sur l’ **[!UICONTROL Segments]** étiquette et cliquez sur **[!UICONTROL Add Segment]**.

   ![](assets/vis_SegmentNew.png)

   Un nouveau segment (nommé Nouveau segment) apparaît dans la visualisation. Le segment Autre représente toutes les données non incluses dans vos segments définis : il s’agit en fait de la différence entre vos données de jeu de données et vos données de segment.

1. Cliquez avec le bouton droit sur le segment nouvellement créé, puis cliquez sur **[!UICONTROL Rename Segment]**.
1. Entrez un nom descriptif pour votre nouveau segment dans le champ du nom.

   >[!NOTE]
   >
   >Si une valeur de mesure, telle qu’un visiteur particulier dans [!DNL Site], répond aux critères de plusieurs segments, la valeur de mesure est incluse dans le premier segment répertorié qu’elle correspond.

**Pour enregistrer la dimension de segment**

1. Cliquez avec le bouton droit de la souris sur l’étiquette Segments, puis cliquez sur **[!UICONTROL Save Dimension]**. La [!DNL Save Dimension As] fenêtre s&#39;affiche. L’emplacement d’enregistrement par défaut est le dossier User\*nom du profil*\Dimensions.
1. Dans le [!DNL File name] champ, saisissez un nom descriptif pour les segments que vous enregistrez en tant que dimension, puis cliquez sur **[!UICONTROL Save]**.

Vous pouvez accéder à la dimension de segment chaque fois que vous travaillez avec une visualisation. Vous pouvez également exporter des données associées aux éléments de votre dimension enregistrée à l’aide de la fonction d’exportation de segments.

Pour plus d’informations sur la fonction d’exportation de segments et des instructions pour la configurer en fonction de vos besoins, voir [Configuration de segments pour l’exportation](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
