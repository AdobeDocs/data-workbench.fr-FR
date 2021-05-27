---
description: Procédure à suivre pour rendre une nouvelle couche de terrain disponible pour affichage dans la visualisation du globe.
title: Mise à disposition d’un nouveau calque d’image du terrain
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
exl-id: 76374298-ed65-4fcf-b40b-be7c15784f40
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 7%

---

# Mise à disposition d’un nouveau calque d’image du terrain{#making-a-new-terrain-image-layer-available}

Procédure à suivre pour rendre une nouvelle couche de terrain disponible pour affichage dans la visualisation du globe.

1. Dans le dossier d’installation Profils\*nom du profil*\Maps dans le répertoire **[!UICONTROL Insight Server]**, placez le fichier de calque et les fichiers image pris en charge.
1. Modifiez le fichier [!DNL order.txt] dans le dossier Profils\*nom du profil*\Maps afin de refléter l’ordre dans lequel vous souhaitez que les calques s’affichent. Par défaut, les calques apparaissent dans l’ordre lexicographique selon leur nom.

   >[!NOTE]
   >
   >Lors de la modification du fichier [!DNL order.txt], veillez à ne pas masquer les calques de carte que vous souhaitez afficher.

   Pour plus d’informations sur l’utilisation des fichiers [!DNL order.txt], consultez le chapitre Configuration de l’interface et des fonctionnalités d’analyse du *Guide de l’utilisateur du Data Workbench*.

1. Dans Data Workbench, sélectionnez le profil souhaité en cliquant avec le bouton droit sur la barre de titre de l’espace de travail, puis en cliquant sur **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]***.
1. Cliquez avec le bouton droit sur la barre de titre de l’espace de travail, puis cliquez sur **[!UICONTROL Work Online]**. Un X apparaît en regard de [!DNL Work Online].
1. Ouvrez un espace de travail et, sur une visualisation en globe, cliquez avec le bouton droit de la souris et sélectionnez le nouveau calque. Un X s’affiche en regard du nom du calque.
