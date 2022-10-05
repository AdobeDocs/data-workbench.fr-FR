---
description: Si vous ne souhaitez pas hériter d’un fichier de configuration d’un profil interne ou d’un autre profil hérité (c’est-à-dire que vous souhaitez que les instructions du fichier soient ignorées lors de la construction du jeu de données), mais que vous ne souhaitez pas modifier le fichier, vous pouvez créer un fichier vide (zéro octet) portant le même nom et stocker le fichier dans un autre profil.
title: Masquage des fichiers de configuration de jeu de données
uuid: eb33cf54-e067-4af2-a10e-7ffe43910e4f
exl-id: 327847d1-421a-4ed1-9a5f-2491765a34bd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 2%

---

# Masquage des fichiers de configuration de jeu de données{#hiding-dataset-configuration-files}

{{eol}}

Si vous ne souhaitez pas hériter d’un fichier de configuration d’un profil interne ou d’un autre profil hérité (c’est-à-dire que vous souhaitez que les instructions du fichier soient ignorées lors de la construction du jeu de données), mais que vous ne souhaitez pas modifier le fichier, vous pouvez créer un fichier vide (zéro octet) portant le même nom et stocker le fichier dans un autre profil.

**Pour zéro octet un fichier de configuration de jeu de données**

1. Dans le [!DNL Profile Manager], ouvrez les dossiers et sous-dossiers nécessaires pour localiser le fichier dont vous souhaitez zéro octet.
1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom du fichier, puis cliquez sur **[!UICONTROL Make Local]**.
1. Ouvrez le fichier local dans un éditeur de texte tel que le Bloc-notes et supprimez son contenu.
1. Enregistrez le fichier, puis fermez-le.
1. Dans le [!DNL Profile Manager], enregistrez le fichier sur zéro octet dans un profil à droite du profil dans lequel réside le fichier d’origine. (Vous souhaitez que le fichier à zéro octet soit prioritaire par rapport au fichier d’origine.)

   Dans le [!DNL Profile Manager], un trait d’union (-), au lieu d’une coche, dans une colonne identifie le fichier à zéro octet comme illustré dans l’exemple ci-dessous.

   ![](assets/vis_ProfileManager_ZeroByteFile.png)

Lorsque vous retraitez votre jeu de données, le jeu de données ne contient pas les composants de jeu de données que le fichier d’origine définit.

>[!NOTE]
>
>Si vous désélectionnez un fichier de configuration qui définit une dimension étendue utilisée dans une visualisation ou une définition de mesure, Data Workbench génère une erreur pour cette visualisation ou mesure, respectivement.

Vous pouvez également utiliser des fichiers sans octet pour déplacer une mesure, une dimension ou un filtre vers un autre emplacement du profil ou pour masquer les éléments de menu. Pour plus d’informations, voir *Guide de l’utilisateur de Data Workbench*.
