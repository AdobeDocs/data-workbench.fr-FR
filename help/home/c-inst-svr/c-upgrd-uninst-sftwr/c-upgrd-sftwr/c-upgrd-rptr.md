---
description: Instructions de mise à niveau de Répéteur à l’aide d’Insight ou de mise à niveau en copiant des fichiers.
title: Mise à niveau de Répéteur
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Mise à niveau de Répéteur{#upgrading-repeater}

Instructions de mise à niveau de Répéteur à l’aide d’Insight ou de mise à niveau en copiant des fichiers.

Vous pouvez utiliser l’une des méthodes suivantes pour mettre à niveau [!DNL Repeater] à partir de Platform 4.x ou version ultérieure :

* Si vous avez créé une connexion entre [!DNL Insight] et [!DNL Repeater] comme décrit dans [Création d’une connexion entre Insight et Répéteur](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118), vous pouvez utiliser [!DNL Insight] pour mettre à niveau [!DNL Repeater]. Voir [Mise à niveau de Répéteur à l’aide d’Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -ou-

* Si vous n’avez pas pu ou n’avez pas créé de connexion entre [!DNL Insight] et [!DNL Repeater], vous devez copier les fichiers de mise à niveau directement sur la machine [!DNL Repeater]. Voir [Mise à niveau de Répéteur par copie de fichiers](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Mise à niveau de Répéteur à l’aide d’Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. Sur l’ordinateur [!DNL Insight], copiez le dossier [!DNL bin] du package de mise à niveau [!DNL Insight Server] dans le dossier [!DNL Temp] du répertoire où est installé [!DNL Insight].
1. Démarrez [!DNL Insight].
1. Dans [!DNL Insight], dans l’onglet [!DNL Admin] > [!DNL Dataset and Profile], cliquez sur la miniature **[!UICONTROL Servers Manager]** pour ouvrir l’espace de travail Gestionnaire de serveurs.
1. Cliquez avec le bouton droit de la souris sur l’icône [!DNL Repeater] que vous souhaitez mettre à niveau, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans la balise [!DNL Server Files Manager], procédez comme suit pour charger les fichiers de mise à niveau sur le serveur :

   1. Recherchez le dossier [!DNL bin] .
   1. Cliquez avec le bouton droit de la souris sur la coche du dossier [!DNL bin] dans le répertoire Temp et sélectionnez **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]***.

>[!NOTE]
>
>Un message s’affiche indiquant que cette étape remplace les fichiers portant le même nom qui existent sur le serveur. Cliquez sur **[!UICONTROL Yes]** pour continuer.

>[!NOTE]
>
>Si vous devez charger des fichiers supplémentaires pour terminer votre mise à niveau [!DNL Repeater], Adobe vous en fournira les instructions.

Après avoir téléchargé les fichiers de mise à niveau sur l’ordinateur [!DNL Repeater], [!DNL Repeater] redémarre automatiquement et charge la nouvelle version.

## Mise à niveau de Répéteur par copie de fichiers {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Ouvrez le fichier de mise à niveau fourni par Adobe. Il est probable que ce fichier soit un fichier [!DNL .zip] pour la mise à niveau de [!DNL Insight Server].
1. Accédez au répertoire dans lequel vous avez installé [!DNL Repeater] (par exemple, [!DNL D:\Adobe\Repeater]).
1. Copiez le dossier [!DNL bin] dans le fichier [!DNL .zip] et collez-le dans le répertoire d’installation [!DNL Repeater] pour remplacer le dossier [!DNL bin] existant.

>[!NOTE]
>
>Si vous devez charger des fichiers supplémentaires pour terminer votre mise à niveau [!DNL Insight Server], Adobe vous en fournira les instructions.

Après avoir copié les fichiers de mise à niveau sur la machine [!DNL Repeater], [!DNL Repeater] redémarre automatiquement et charge la nouvelle version.
