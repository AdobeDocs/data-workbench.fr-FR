---
description: Pour créer une dimension de segment, vous commencez par effectuer une sélection dans un espace de travail, puis vous ajoutez le segment à une visualisation.
title: Créer des dimensions de segment
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
exl-id: 393d544e-e821-49e3-8cfb-5a3496aa7380
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 3%

---

# Créer des dimensions de segment{#create-a-segment-dimensions}

{{eol}}

Pour créer une dimension de segment, vous commencez par effectuer une sélection dans un espace de travail, puis vous ajoutez le segment à une visualisation.

**Pour créer une dimension de segment**

1. Ajoutez une visualisation de segment à l’espace de travail. Par exemple :

   ![](assets/vis_Segment.png)

1. Ajoutez à votre espace de travail les visualisations que vous souhaitez utiliser pour définir votre segment, puis effectuez les sélections de votre choix pour définir votre segment.
1. Dans la visualisation de segment, cliquez avec le bouton droit sur le libellé du segment après lequel vous souhaitez ajouter le nouveau segment, puis cliquez sur **[!UICONTROL Add Segment]**.

   >[!NOTE]
   >
   >Pour créer un nouveau premier segment, cliquez avec le bouton droit de la souris sur le **[!UICONTROL Segments]** libellé et clic **[!UICONTROL Add Segment]**.

   ![](assets/vis_SegmentNew.png)

   Un nouveau segment (nommé Nouveau segment) apparaît dans la visualisation. Le segment Autre représente toutes les données qui ne sont pas incluses dans vos segments définis : il s’agit effectivement de la différence entre les données de votre jeu de données et celles de votre segment.

1. Cliquez avec le bouton droit sur le segment nouvellement créé, puis cliquez sur **[!UICONTROL Rename Segment]**.
1. Saisissez un nom explicite pour votre nouveau segment dans le champ Nom.

   >[!NOTE]
   >
   >Si une valeur de mesure, telle qu’un visiteur particulier dans [!DNL Site], répond aux critères de plusieurs segments, la valeur de mesure n’est incluse dans que le premier segment répertorié correspondant.

**Pour enregistrer la dimension de segment**

1. Cliquez avec le bouton droit de la souris sur le libellé Segments, puis cliquez sur **[!UICONTROL Save Dimension]**. Le [!DNL Save Dimension As] s’affiche. L’emplacement d’enregistrement par défaut est le dossier User\*profile name*\Dimensions .
1. Dans le [!DNL File name] , saisissez un nom descriptif pour les segments que vous enregistrez en tant que dimension, puis cliquez sur **[!UICONTROL Save]**.

Vous pouvez accéder à la dimension de segment lorsque vous travaillez avec une visualisation. Vous pouvez également exporter des données associées aux éléments de votre dimension enregistrée à l’aide de la fonction d’exportation de segments.

Pour plus d’informations sur la fonction d’exportation de segments et des instructions pour la configurer selon vos besoins, voir [Configuration de segments à exporter](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
