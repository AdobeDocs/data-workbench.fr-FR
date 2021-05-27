---
description: Les nouvelles dimensions que vous créez à l’aide de Data Workbench (appelées dimensions dérivées) sont des dimensions côté client.
title: Utilisation de dimensions dérivées
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
exl-id: 5b7e3a2a-ac61-4186-ad6c-234edf68af3e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 1%

---

# Utilisation de dimensions dérivées{#work-with-derived-dimensions}

Les nouvelles dimensions que vous créez à l’aide de Data Workbench (appelées dimensions dérivées) sont des dimensions côté client.

Au lieu de définir ces dimensions lors du processus de construction et de mise à jour du jeu de données (dans le fichier [!DNL Transformation.cfg]) sur vos ordinateurs de serveur Data Workbench, les dimensions dérivées sont créées et stockées individuellement sous la forme de fichiers [!DNL .dim] dans un profil. Par conséquent, vous pouvez modifier des dimensions existantes et créer de nouvelles dimensions dérivées sans retraiter votre jeu de données.

>[!NOTE]
>
>Pour plus d’informations sur les dimensions que celles de cette section, consultez le guide de l’application de Data Workbench approprié.

Pour plus d’informations sur la configuration du jeu de données et le processus de mise à jour, consultez le *Guide de configuration du jeu de données*.

## Créer des dimensions dérivées {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

Pour créer une dimension dérivée, vous pouvez copier et modifier une dimension existante ou enregistrer une dimension à partir d’une visualisation.

## Créer des dimensions dérivées à partir d’une dimension existante {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

Les utilisateurs souhaitent le plus souvent créer de nouvelles dimensions temporelles à partir de dimensions existantes. Par exemple, vous pouvez créer une nouvelle dimension &quot;5 derniers jours&quot; à partir de la dimension &quot;7 derniers jours&quot; existante.

1. Dans la colonne [!DNL Profile Manager], dans la colonne *nom du profil*, cliquez avec le bouton droit de la souris sur la coche d’une dimension similaire à la dimension que vous souhaitez créer, puis cliquez sur **[!UICONTROL Copy]**.

   Par exemple, pour copier la balise [!DNL Last 7 Days.dim] du dossier Reporting du profil [!DNL Traffic], cliquez avec le bouton droit de la souris sur la coche du nom du fichier dans la colonne [!DNL Traffic] et cliquez sur **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Cliquez avec le bouton droit dans la colonne [!DNL User] du dossier dans lequel vous souhaitez stocker la dimension copiée, puis cliquez sur **[!UICONTROL Paste]**.

   La dimension apparaît dans le dossier Dimensions sélectionné avec une coche dans la colonne [!DNL User].

1. Pour renommer la nouvelle dimension, cliquez avec le bouton droit de la souris sur sa coche dans la colonne [!DNL User] et saisissez le nouveau nom dans le champ [!DNL File].
1. Dans le menu contextuel, cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Les paramètres de définition de la dimension apparaissent.
1. Modifiez les paramètres selon les besoins pour définir la nouvelle dimension.

   Pour les dimensions temporelles, vous devez probablement modifier uniquement les paramètres Nombre et Plage .

1. Pour enregistrer le fichier, cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   Si vous souhaitez que tous les utilisateurs d’un profil utilisent la dimension que vous avez créée, vous devez la charger dans le profil à l’aide de [!DNL Profile Manager]. Pour plus d’informations, voir [Publication de fichiers dans votre profil de travail](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

Vous pouvez désormais utiliser la nouvelle dimension dans le profil actuel en la sélectionnant comme vous le feriez pour toute dimension intégrée.

## Enregistrement d’une dimension à partir d’une visualisation {#section-84cfe5e9ccb640afa2ee4e2da2682757}

Vous pouvez enregistrer les dimensions étendues des mappages de processus et des segments. Pour connaître les étapes d’enregistrement d’une dimension à partir d’une cartographie des processus, voir [Enregistrement de Dimensions à partir de cartographies des processus](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051). Pour connaître les étapes d’enregistrement d’une dimension de segment, voir [Création de Dimensions de segment](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) à la page 82.

## Enregistrement d’un segment en tant que dimension {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

Vous pouvez également enregistrer les segments définis en tant que dimension. Pour connaître les étapes, voir [Réutilisation d’une visualisation de segment](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc).

## Modifier une dimension dérivée existante {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   Dans la colonne [!DNL Profile Manager], dans la colonne *nom du profil*, cliquez avec le bouton droit de la souris sur la coche du fichier de dimension à modifier, puis cliquez sur **[!UICONTROL Make Local]**.
1. Cliquez avec le bouton droit de la souris sur la coche du fichier de dimension dans la colonne [!DNL User] et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Renseignez les paramètres selon vos besoins. Pour plus d’informations, contactez les Services de conseil Adobe.
1. Pour enregistrer le fichier, cliquez avec le bouton droit de la souris sur **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   Si vous souhaitez que tous les utilisateurs d’un profil utilisent la dimension modifiée, vous devez la charger dans le profil à l’aide de la balise [!DNL Profile Manager]. Pour plus d’informations, voir [Publication de fichiers dans votre profil de travail](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
