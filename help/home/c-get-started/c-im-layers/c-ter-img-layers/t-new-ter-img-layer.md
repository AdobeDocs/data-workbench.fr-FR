---
description: Cette section décrit la marche à suivre pour rendre n’importe quelle couche de terrain disponible pour l’affichage sur la visualisation du globe.
title: Mettre à disposition un nouveau calque d’image du terrain
uuid: 8fb98a3e-6335-4922-a1e6-35c92b19e2ec
exl-id: bf0e6b37-4c8a-4d50-8bc9-eb70ca1cbb23
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 7%

---

# Mettre à disposition un nouveau calque d’image du terrain{#make-a-new-terrain-image-layer-available}

Cette section décrit la marche à suivre pour rendre n’importe quelle couche de terrain disponible pour l’affichage sur la visualisation du globe.

1. Dans le dossier Profils\*nom du profil*\Maps du répertoire d’installation du serveur Data Workbench, importez le fichier de calque et les fichiers image pris en charge.
1. Modifiez le fichier [!DNL order.txt] dans le dossier Profils\*nom du profil*\Maps afin de refléter l’ordre dans lequel les calques doivent s’afficher. Par défaut, les calques apparaissent par leur nom dans l’ordre lexicographique.

   >[!NOTE]
   >
   >Lorsque vous modifiez le fichier [!DNL order.txt], veillez à ne pas masquer les calques de mappage que vous souhaitez afficher.

   Pour plus d&#39;informations sur l&#39;utilisation des fichiers [!DNL order.txt], consultez le chapitre Configuration des fonctionnalités d&#39;interface et d&#39;Analyse du *Guide de l&#39;utilisateur Data Workbench*.

1. Dans le Data Workbench, sélectionnez le profil de votre choix en cliquant avec le bouton droit sur la barre de titre de l’espace de travail et en cliquant sur **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]***.
1. Cliquez avec le bouton droit sur la barre de titre de l&#39;espace de travail, puis cliquez sur **[!UICONTROL Work Online]**. Un X apparaît en regard de Travailler en ligne.
1. Ouvrez un espace de travail et, sur une visualisation globe, cliquez avec le bouton droit de la souris et sélectionnez le nouveau calque. Un X apparaît en regard du nom du calque.
