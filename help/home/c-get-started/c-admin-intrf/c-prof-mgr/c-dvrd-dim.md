---
description: Les nouvelles dimensions que vous créez à l’aide des outils de données (appelées dimensions dérivées) sont des dimensions côté client.
solution: Analytics
title: Utilisation de dimensions dérivées
topic: Data workbench
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Utilisation de dimensions dérivées{#work-with-derived-dimensions}

Les nouvelles dimensions que vous créez à l’aide des outils de données (appelées dimensions dérivées) sont des dimensions côté client.

Au lieu de définir ces dimensions lors du processus de création et de mise à jour du jeu de données (dans le [!DNL Transformation.cfg] fichier) sur les ordinateurs de votre serveur Outils de données, les dimensions dérivées sont créées et stockées individuellement sous forme de [!DNL .dim] fichiers dans un profil. Par conséquent, vous pouvez modifier des dimensions existantes et créer de nouvelles dimensions dérivées sans retraiter votre jeu de données.

>[!NOTE]
>
>Pour plus d’informations sur les dimensions que celles fournies dans cette section, voir le guide de l’application Outils de données approprié.

Pour plus d&#39;informations sur la configuration des jeux de données et le processus de mise à jour, consultez le Guide *de configuration des jeux de* données.

## Création de dimensions dérivées {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

Pour créer une dimension dérivée, vous pouvez copier et modifier une dimension existante ou enregistrer une dimension à partir d’une visualisation.

## Création de dimensions dérivées à partir d’une dimension existante {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

Les utilisateurs souhaitent le plus souvent créer de nouvelles dimensions temporelles à partir des dimensions existantes. Par exemple, vous pouvez créer une nouvelle dimension &quot;5 derniers jours&quot; à partir de la dimension existante &quot;7 derniers jours&quot;.

1. Dans la [!DNL Profile Manager]colonne Nom *du* profil, cliquez avec le bouton droit de la souris sur la coche d’une dimension semblable à celle que vous souhaitez créer, puis cliquez sur **[!UICONTROL Copy]**.

   Par exemple, pour copier le fichier [!DNL Last 7 Days.dim] du dossier Création de rapports du [!DNL Traffic] profil, cliquez avec le bouton droit de la souris sur la coche correspondant au nom du fichier dans la [!DNL Traffic] colonne et cliquez sur **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Cliquez avec le bouton droit dans la [!DNL User] colonne du dossier dans lequel vous souhaitez stocker la dimension copiée, puis cliquez sur **[!UICONTROL Paste]**.

   La dimension apparaît dans le dossier Dimensions sélectionné avec une coche dans la [!DNL User] colonne.

1. Pour renommer la nouvelle dimension, cliquez avec le bouton droit de la souris sur sa coche dans la [!DNL User] colonne et saisissez le nouveau nom dans le [!DNL File] champ.
1. Dans le menu contextuel, cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Les paramètres de définition de la dimension apparaissent.
1. Modifiez les paramètres en fonction des besoins pour définir la nouvelle dimension.

   Pour les dimensions temporelles, vous devez probablement modifier uniquement les paramètres Nombre et Plage.

1. Pour enregistrer le fichier, cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   Si vous souhaitez que tous les utilisateurs d’un profil utilisent la dimension que vous avez créée, vous devez la télécharger vers le profil à l’aide de la [!DNL Profile Manager]. Pour plus d’informations, voir [Publication de fichiers dans votre profil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)de travail.

Vous pouvez désormais utiliser la nouvelle dimension dans le profil actuel en la sélectionnant comme vous le feriez pour toute dimension intégrée.

## Enregistrement d’une dimension à partir d’une visualisation {#section-84cfe5e9ccb640afa2ee4e2da2682757}

Vous pouvez enregistrer des dimensions étendues dans les mappages de processus et les segments. Pour connaître les étapes d’enregistrement d’une dimension à partir d’un mappage de processus, voir [Enregistrement de dimensions à partir de mappages](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051)de processus. Pour connaître les étapes d’enregistrement d’une dimension de segment, voir [Création de dimensions](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) de segment à la page 82.

## Enregistrement d’un segment en tant que dimension {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

Vous pouvez également enregistrer les segments définis en tant que dimension. Pour connaître les étapes, voir [Réutilisation d’une visualisation](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc)de segment.

## Modification d’une dimension dérivée existante {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   Dans la [!DNL Profile Manager]colonne Nom *du* profil, cliquez avec le bouton droit de la souris sur la coche correspondant au fichier de dimension à modifier, puis cliquez sur **[!UICONTROL Make Local]**.
1. Cliquez avec le bouton droit de la souris sur la coche du fichier de dimension dans la [!DNL User] colonne et cliquez sur **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.
1. Renseignez les paramètres si nécessaire. Pour plus d’informations, contactez les services de conseil Adobe.
1. Pour enregistrer le fichier, cliquez avec le bouton droit **[!UICONTROL (modified)]** en haut de la fenêtre et cliquez sur **[!UICONTROL Save]**.

   Si vous souhaitez que tous les utilisateurs d’un profil utilisent la dimension modifiée, vous devez la télécharger vers le profil à l’aide de la [!DNL Profile Manager]. Pour plus d’informations, voir [Publication de fichiers dans votre profil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)de travail.

