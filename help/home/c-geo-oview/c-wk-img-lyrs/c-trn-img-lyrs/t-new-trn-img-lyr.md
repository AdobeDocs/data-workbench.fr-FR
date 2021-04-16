---
description: Procédure à suivre pour rendre une nouvelle couche de terrain disponible pour l’affichage sur la visualisation du globe.
title: Mise à disposition d’un nouveau calque d’image du terrain
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
exl-id: 76374298-ed65-4fcf-b40b-be7c15784f40
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 7%

---

# Mise à disposition d’un nouveau calque d’image du terrain{#making-a-new-terrain-image-layer-available}

Procédure à suivre pour rendre une nouvelle couche de terrain disponible pour l’affichage sur la visualisation du globe.

1. Dans le dossier Profils\*nom du profil*\Maps du répertoire d&#39;installation **[!UICONTROL Insight Server]**, importez le fichier de calque et les fichiers image pris en charge.
1. Modifiez le fichier [!DNL order.txt] dans le dossier Profils\*nom du profil*\Maps afin de refléter l’ordre dans lequel les calques doivent s’afficher. Par défaut, les calques apparaissent par leur nom dans l’ordre lexicographique.

   >[!NOTE]
   >
   >Lorsque vous modifiez le fichier [!DNL order.txt], veillez à ne pas masquer les calques de mappage que vous souhaitez afficher.

   Pour plus d&#39;informations sur l&#39;utilisation des fichiers [!DNL order.txt], consultez le chapitre Configuration des fonctionnalités d&#39;interface et d&#39;Analyse du *Guide de l&#39;utilisateur Data Workbench*.

1. Dans les outils de données, sélectionnez le profil de votre choix en cliquant avec le bouton droit sur la barre de titre de l’espace de travail et en cliquant sur **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]***.
1. Cliquez avec le bouton droit sur la barre de titre de l&#39;espace de travail, puis cliquez sur **[!UICONTROL Work Online]**. Un X apparaît en regard de [!DNL Work Online].
1. Ouvrez un espace de travail et, sur une visualisation globe, cliquez avec le bouton droit de la souris et sélectionnez le nouveau calque. Un X apparaît en regard du nom du calque.
