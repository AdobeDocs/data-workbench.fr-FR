---
description: Instructions de mise à niveau de Répéteur à l’aide d’Insight ou de mise à niveau en copiant des fichiers.
title: Mise à niveau de Répéteur
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Mise à niveau de Répéteur{#upgrading-repeater}

{{eol}}

Instructions de mise à niveau de Répéteur à l’aide d’Insight ou de mise à niveau en copiant des fichiers.

Vous pouvez utiliser l’une des méthodes suivantes pour effectuer la mise à niveau : [!DNL Repeater] de Platform 4.x ou version ultérieure :

* Si vous avez créé une connexion entre [!DNL Insight] et [!DNL Repeater] comme décrit dans [Création d’une connexion entre Insight et Répéteur](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118), vous pouvez utiliser [!DNL Insight] à la mise à niveau [!DNL Repeater]. Voir [Mise à niveau de Répéteur à l’aide d’Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -ou-

* Si vous n’avez pas pu ou n’avez pas créé de connexion entre [!DNL Insight] et [!DNL Repeater], vous devez copier les fichiers de mise à niveau directement dans le [!DNL Repeater] machine. Voir [Mise à niveau de Répéteur par copie de fichiers](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Mise à niveau de Répéteur à l’aide d’Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. Sur le [!DNL Insight] , copiez la variable [!DNL bin] à partir du dossier [!DNL Insight Server] le package de mise à niveau vers [!DNL Temp] dans le répertoire où [!DNL Insight] est installé.
1. Début [!DNL Insight].
1. Dans [!DNL Insight], sur le [!DNL Admin] > [!DNL Dataset and Profile] , cliquez sur l’onglet **[!UICONTROL Servers Manager]** miniature pour ouvrir l’espace de travail Gestionnaire de serveurs .
1. Cliquez avec le bouton droit de la souris sur l’icône du [!DNL Repeater] vous souhaitez effectuer la mise à niveau, puis cliquez sur **[!UICONTROL Server Files]**.
1. Dans le [!DNL Server Files Manager], procédez comme suit pour charger les fichiers de mise à niveau sur le serveur :

   1. Recherchez la variable [!DNL bin] dossier.
   1. Cliquez avec le bouton droit de la souris sur la coche correspondant au [!DNL bin] dans le répertoire Temp et sélectionnez **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Un message s’affiche indiquant que cette étape remplace les fichiers portant le même nom qui existent sur le serveur. Cliquez sur **[!UICONTROL Yes]** pour continuer.

>[!NOTE]
>
>Si vous devez charger des fichiers supplémentaires pour terminer votre [!DNL Repeater] mise à niveau, Adobe vous fournira des instructions à ce sujet.

Après avoir chargé les fichiers de mise à niveau dans le [!DNL Repeater] machine, [!DNL Repeater] redémarre automatiquement et charge la nouvelle version.

## Mise à niveau de Répéteur par copie de fichiers {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Ouvrez le fichier de mise à niveau fourni par Adobe. Ce fichier est probablement un [!DNL .zip] fichier pour la mise à niveau [!DNL Insight Server].
1. Accédez au répertoire dans lequel vous avez installé [!DNL Repeater] (par exemple, [!DNL D:\Adobe\Repeater]).
1. Copiez le [!DNL bin] dans le dossier [!DNL .zip] et collez-les dans votre [!DNL Repeater] répertoire d’installation pour remplacer le répertoire existant [!DNL bin] dossier.

>[!NOTE]
>
>Si vous devez charger des fichiers supplémentaires pour terminer votre [!DNL Insight Server] mise à niveau, Adobe vous fournira des instructions à ce sujet.

Après avoir copié les fichiers de mise à niveau dans la [!DNL Repeater] machine, [!DNL Repeater] redémarre automatiquement et charge la nouvelle version.
