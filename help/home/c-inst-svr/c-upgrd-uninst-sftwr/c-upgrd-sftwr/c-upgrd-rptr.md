---
description: Instructions de mise à niveau de Repeater à l’aide d’Insight ou de mise à niveau en copiant des fichiers.
title: Mise à niveau de Répéteur
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Mise à niveau de Répéteur{#upgrading-repeater}

Instructions de mise à niveau de Repeater à l’aide d’Insight ou de mise à niveau en copiant des fichiers.

Vous pouvez utiliser l&#39;une des méthodes suivantes pour mettre à niveau [!DNL Repeater] à partir de la plate-forme 4.x ou ultérieure :

* Si vous avez créé une connexion entre [!DNL Insight] et [!DNL Repeater] comme décrit dans [Création d&#39;une connexion entre Insight et Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118), vous pouvez utiliser [!DNL Insight] pour mettre à niveau [!DNL Repeater]. Voir [Mise à niveau de Repeater à l’aide d’Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -ou-

* Si vous n&#39;avez pas pu ou n&#39;avez pas créé de connexion entre [!DNL Insight] et [!DNL Repeater], vous devez copier les fichiers de mise à niveau directement sur l&#39;ordinateur [!DNL Repeater]. Voir [Mise à niveau de Repeater en copiant des fichiers](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Mise à niveau de Repeater à l’aide d’Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. Sur l&#39;ordinateur [!DNL Insight], copiez le dossier [!DNL bin] du package de mise à niveau [!DNL Insight Server] dans le dossier [!DNL Temp] du répertoire où [!DNL Insight] est installé.
1. Début [!DNL Insight].
1. Dans [!DNL Insight], sur l&#39;onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l&#39;espace de travail Servers Manager.
1. Cliquez avec le bouton droit de la souris sur l&#39;icône [!DNL Repeater] que vous souhaitez mettre à niveau et cliquez sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], procédez comme suit pour télécharger les fichiers de mise à niveau vers le serveur :

   1. Recherchez le dossier [!DNL bin].
   1. Cliquez avec le bouton droit de la souris sur la coche du dossier [!DNL bin] dans le répertoire Temp et sélectionnez **[!UICONTROL Save Directory to]** > *&lt; &lt;a3/&quot;*.**[!UICONTROL server name]**

>[!NOTE]
>
>Un message s’affiche indiquant que cette étape remplace les fichiers du même nom qui existent sur le serveur. Cliquez sur **[!UICONTROL Yes]** pour continuer.

>[!NOTE]
>
>Si vous devez télécharger d&#39;autres fichiers pour effectuer votre mise à niveau [!DNL Repeater], l&#39;Adobe vous en fournira les instructions.

Après avoir téléchargé les fichiers de mise à niveau sur l’ordinateur [!DNL Repeater], [!DNL Repeater] se redémarre automatiquement et charge la nouvelle version.

## Mise à niveau de Repeater par Copie de fichiers {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Ouvrez le fichier de mise à niveau fourni par Adobe. Il s’agit probablement d’un fichier [!DNL .zip] destiné à la mise à niveau de [!DNL Insight Server].
1. Accédez au répertoire dans lequel vous avez installé [!DNL Repeater] (par exemple, [!DNL D:\Adobe\Repeater]).
1. Copiez le dossier [!DNL bin] dans le fichier [!DNL .zip] et collez-le dans votre répertoire d&#39;installation [!DNL Repeater] pour remplacer le dossier [!DNL bin] existant.

>[!NOTE]
>
>Si vous devez télécharger d&#39;autres fichiers pour effectuer votre mise à niveau [!DNL Insight Server], l&#39;Adobe vous en fournira les instructions.

Après avoir copié les fichiers de mise à niveau sur l&#39;ordinateur [!DNL Repeater], [!DNL Repeater] redémarre automatiquement et charge la nouvelle version.
