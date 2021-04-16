---
description: Pour créer une dimension de segment, vous commencez par faire une sélection dans un espace de travail, puis vous ajoutez le segment à une visualisation.
title: Créer des dimensions de segment
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
exl-id: 393d544e-e821-49e3-8cfb-5a3496aa7380
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 3%

---

# Créer des dimensions de segment{#create-a-segment-dimensions}

Pour créer une dimension de segment, vous commencez par faire une sélection dans un espace de travail, puis vous ajoutez le segment à une visualisation.

**Pour créer une dimension de segment**

1. Ajoutez une visualisation des segments dans l’espace de travail. Par exemple :

   ![](assets/vis_Segment.png)

1. Ajoutez des visualisations dans l’espace de travail que vous souhaitez utiliser pour définir votre segment, puis effectuez les sélections souhaitées pour définir votre segment.
1. Dans la visualisation du segment, cliquez avec le bouton droit de la souris sur l’étiquette du segment après lequel vous souhaitez ajouter le nouveau segment, puis cliquez sur **[!UICONTROL Add Segment]**.

   >[!NOTE]
   >
   >Pour créer un nouveau premier segment, cliquez avec le bouton droit de la souris sur l&#39;étiquette **[!UICONTROL Segments]** et cliquez sur **[!UICONTROL Add Segment]**.

   ![](assets/vis_SegmentNew.png)

   Un nouveau segment (nommé Nouveau segment) s’affiche dans la visualisation. Le segment Autre représente toutes les données qui ne sont pas incluses dans les segments définis : il s’agit effectivement de la différence entre les données de votre jeu de données et celles de vos segments.

1. Cliquez avec le bouton droit sur le segment nouvellement créé, puis cliquez sur **[!UICONTROL Rename Segment]**.
1. Entrez un nom descriptif pour votre nouveau segment dans le champ Nom.

   >[!NOTE]
   >
   >Si une valeur de mesure, telle qu’un visiteur particulier dans [!DNL Site], répond aux critères de plusieurs segments, la valeur de mesure est incluse dans le premier segment répertorié qu’elle correspond.

**Pour enregistrer la dimension de segment**

1. Cliquez avec le bouton droit de la souris sur l’étiquette Segments, puis cliquez sur **[!UICONTROL Save Dimension]**. La fenêtre [!DNL Save Dimension As] s&#39;affiche. L&#39;emplacement d&#39;enregistrement par défaut est le dossier User\*profil name*\Dimensions.
1. Dans le champ [!DNL File name], saisissez un nom descriptif pour les segments que vous enregistrez en tant que dimension et cliquez sur **[!UICONTROL Save]**.

Vous pouvez accéder à la dimension de segment chaque fois que vous travaillez avec une visualisation. Vous pouvez également exporter des données associées aux éléments de votre dimension enregistrée à l’aide de la fonction d’exportation de segments.

Pour plus d&#39;informations sur la fonction d&#39;exportation de segments et des instructions pour la configurer en fonction de vos besoins, voir [Configuration de segments pour l&#39;exportation](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
