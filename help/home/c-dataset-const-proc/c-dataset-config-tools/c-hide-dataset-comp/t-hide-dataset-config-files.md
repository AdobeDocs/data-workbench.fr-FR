---
description: Si vous ne souhaitez pas hériter d’un fichier de configuration d’un profil interne ou d’un autre profil hérité (c’est-à-dire que vous souhaitez que les instructions du fichier soient ignorées lors de la construction du jeu de données), mais que vous ne souhaitez pas modifier le fichier, vous pouvez créer un fichier vide (zéro octet) portant le même nom et stocker le fichier dans un autre profil.
solution: Analytics
title: Masquage des fichiers de configuration des jeux de données
topic: Data workbench
uuid: eb33cf54-e067-4af2-a10e-7ffe43910e4f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Masquage des fichiers de configuration des jeux de données{#hiding-dataset-configuration-files}

Si vous ne souhaitez pas hériter d’un fichier de configuration d’un profil interne ou d’un autre profil hérité (c’est-à-dire que vous souhaitez que les instructions du fichier soient ignorées lors de la construction du jeu de données), mais que vous ne souhaitez pas modifier le fichier, vous pouvez créer un fichier vide (zéro octet) portant le même nom et stocker le fichier dans un autre profil.

**Pour obtenir un fichier de configuration de jeu de données à zéro octet**

1. Dans la [!DNL Profile Manager]section, ouvrez les dossiers et sous-dossiers nécessaires pour localiser le fichier à zéro octet.
1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom du fichier, puis cliquez sur **[!UICONTROL Make Local]**.
1. Ouvrez le fichier local dans un éditeur de texte tel que le Bloc-notes et supprimez son contenu.
1. Enregistrez et fermez le fichier.
1. Dans la [!DNL Profile Manager]section, enregistrez le fichier sur zéro octet dans un profil à droite du profil dans lequel réside le fichier d’origine. (Vous souhaitez que le fichier à zéro octet soit prioritaire sur le fichier d’origine.)

   Dans la colonne [!DNL Profile Manager], un trait d’union (-), au lieu d’une coche, identifie le fichier à zéro octet, comme illustré dans l’exemple ci-dessous.

   ![](assets/vis_ProfileManager_ZeroByteFile.png)

Lorsque vous retraitez votre jeu de données, celui-ci ne contient pas les composants de jeu de données définis par le fichier d’origine.

>[!NOTE]
>
>Si vous créez un fichier de configuration à zéro octet qui définit une dimension étendue utilisée dans une visualisation ou une définition de mesure, l’outil de données génère une erreur pour cette visualisation ou mesure, respectivement.

Vous pouvez également utiliser des fichiers à zéro octet pour déplacer une mesure, une dimension ou un filtre vers un autre emplacement du profil ou pour masquer des éléments de menu. For information, see the *Data Workbench User Guide*.
