---
description: Instructions de mise à niveau de Repeater à l’aide d’Insight ou de mise à niveau en copiant des fichiers.
solution: Analytics
title: Mise à niveau de Répéteur
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---


# Mise à niveau de Répéteur{#upgrading-repeater}

Instructions de mise à niveau de Repeater à l’aide d’Insight ou de mise à niveau en copiant des fichiers.

Vous pouvez utiliser l’une des méthodes suivantes pour effectuer une mise à niveau [!DNL Repeater] à partir de la plate-forme 4.x ou d’une version ultérieure :

* Si vous avez créé une connexion entre [!DNL Insight] et [!DNL Repeater] comme décrit dans [Création d’une connexion entre Insight et Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118), vous pouvez utiliser [!DNL Insight] pour la mise à niveau [!DNL Repeater]. Voir [Mise à niveau de Repeater à l’aide d’Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -ou-

* Si vous n&#39;avez pas pu ou n&#39;avez pas créé de connexion entre [!DNL Insight] et [!DNL Repeater], vous devez copier les fichiers de mise à niveau directement sur l&#39; [!DNL Repeater] ordinateur. Voir [Mise à niveau de Repeater en copiant des fichiers](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Mise à niveau de Repeater à l’aide d’Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. Sur l’ [!DNL Insight] ordinateur, copiez le [!DNL bin] dossier du package [!DNL Insight Server] de mise à niveau vers le [!DNL Temp] dossier du répertoire dans lequel [!DNL Insight] est installé.
1. Start [!DNL Insight].
1. Dans [!DNL Insight]l’onglet [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur la **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Servers Manager.
1. Cliquez avec le bouton droit de la souris sur l’icône de la [!DNL Repeater] mise à niveau, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], procédez comme suit pour télécharger les fichiers de mise à niveau vers le serveur :

   1. Localisez le [!DNL bin] dossier.
   1. Cliquez avec le bouton droit de la souris sur la coche correspondant au [!DNL bin] dossier dans le répertoire Temp et sélectionnez **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Un message s’affiche indiquant que cette étape remplace les fichiers du même nom qui existent sur le serveur. Click **[!UICONTROL Yes]** to continue.

>[!NOTE]
>
>Si vous devez télécharger des fichiers supplémentaires pour terminer votre [!DNL Repeater] mise à niveau, l’Adobe vous en fournira les instructions.

Après avoir téléchargé les fichiers de mise à niveau sur l’ [!DNL Repeater] ordinateur, [!DNL Repeater] redémarre automatiquement et charge la nouvelle version.

## Mise à niveau de Repeater en copiant des fichiers {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Ouvrez le fichier de mise à niveau fourni par Adobe. Il s’agit probablement d’un [!DNL .zip] fichier à mettre à niveau [!DNL Insight Server].
1. Accédez au répertoire dans lequel vous avez installé [!DNL Repeater] (par exemple, [!DNL D:\Adobe\Repeater]).
1. Copiez le [!DNL bin] dossier dans le [!DNL .zip] fichier et collez-le dans le répertoire [!DNL Repeater] d’installation pour remplacer le [!DNL bin] dossier existant.

>[!NOTE]
>
>Si vous devez télécharger des fichiers supplémentaires pour terminer votre [!DNL Insight Server] mise à niveau, l’Adobe vous en fournira les instructions.

Après avoir copié les fichiers de mise à niveau sur l’ [!DNL Repeater] ordinateur, [!DNL Repeater] redémarre automatiquement et charge la nouvelle version.
