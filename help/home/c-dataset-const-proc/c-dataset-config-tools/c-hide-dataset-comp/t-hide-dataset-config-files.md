---
description: Si vous ne souhaitez pas hériter d'un fichier de configuration d'un profil interne ou d'un autre  hérité (c'est-à-dire que les instructions du fichier doivent être ignorées lors de la construction du jeu de données), mais que vous ne souhaitez pas modifier le fichier, vous pouvez créer un fichier vide (zéro octet) portant le même nom et stocker le fichier dans un autre profil.
title: Masquage des fichiers de configuration de jeu de données
uuid: eb33cf54-e067-4af2-a10e-7ffe43910e4f
exl-id: 327847d1-421a-4ed1-9a5f-2491765a34bd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 2%

---

# Masquage des fichiers de configuration de jeu de données{#hiding-dataset-configuration-files}

Si vous ne souhaitez pas hériter d&#39;un fichier de configuration d&#39;un profil interne ou d&#39;un autre  hérité (c&#39;est-à-dire que les instructions du fichier doivent être ignorées lors de la construction du jeu de données), mais que vous ne souhaitez pas modifier le fichier, vous pouvez créer un fichier vide (zéro octet) portant le même nom et stocker le fichier dans un autre profil.

**Pour obtenir un fichier de configuration de jeu de données sur zéro octet**

1. Dans [!DNL Profile Manager], ouvrez les dossiers et sous-dossiers nécessaires pour localiser le fichier à zéro octet.
1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom du fichier et cliquez sur **[!UICONTROL Make Local]**.
1. Ouvrez le fichier local dans un éditeur de texte tel que le Bloc-notes et supprimez son contenu.
1. Enregistrez et fermez le fichier.
1. Dans [!DNL Profile Manager], enregistrez le fichier sur zéro octet dans un profil à droite du profil dans lequel réside le fichier d’origine. (Vous souhaitez que le fichier à zéro octet soit prioritaire sur le fichier d’origine.)

   Dans le [!DNL Profile Manager], un trait d’union (-), au lieu d’une coche, identifie dans une colonne le fichier à zéro octet, comme illustré dans l’exemple ci-dessous.

   ![](assets/vis_ProfileManager_ZeroByteFile.png)

Lorsque vous retraitez votre jeu de données, celui-ci ne contient pas les composants de jeu de données définis par le fichier d&#39;origine.

>[!NOTE]
>
>Si vous créez un fichier de configuration sur zéro octet qui définit une dimension étendue utilisée dans une visualisation ou une définition de mesure, l’outil de données génère une erreur pour cette visualisation ou cette mesure, respectivement.

Vous pouvez également utiliser des fichiers à zéro octet pour déplacer une mesure, une dimension ou un filtre vers un autre emplacement du profil ou pour masquer les options de menu. Pour plus d&#39;informations, consultez le *Guide de l&#39;utilisateur Data Workbench*.
