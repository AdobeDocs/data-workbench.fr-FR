---
description: Cette section décrit la procédure à suivre pour rendre n’importe quel calque vectoriel disponible à afficher sur la visualisation en globe.
title: Mettre à disposition un nouveau calque vectoriel
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
exl-id: 6c084bac-1a6d-452a-bf07-e502d0f2145a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 7%

---

# Mettre à disposition un nouveau calque vectoriel{#make-a-new-vector-layer-available}

Cette section décrit la procédure à suivre pour rendre n’importe quel calque vectoriel disponible à afficher sur la visualisation en globe.

1. Dans le dossier Profils\*nom du profil*\Maps du répertoire d’installation du serveur Data Workbench, placez le fichier de calque et les fichiers [!DNL .vec] ou [!DNL .tsv].
1. Modifiez le fichier [!DNL order.txt] dans le dossier Profils\*nom du profil*\Maps afin de refléter l’ordre dans lequel les calques doivent s’afficher. Par défaut, les calques apparaissent par leur nom dans l’ordre lexicographique.

   >[!NOTE]
   >
   >Lorsque vous modifiez le fichier [!DNL order.txt], veillez à ne pas masquer les calques de mappage que vous souhaitez afficher.

   Pour plus d&#39;informations sur l&#39;utilisation des fichiers [!DNL order.txt], voir [Personnalisation des menus à l&#39;aide de fichiers Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

1. Dans Insight, sélectionnez le profil de votre choix en cliquant avec le bouton droit sur la barre de titre de l’espace de travail et en cliquant sur **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]***.
1. Cliquez avec le bouton droit sur la barre de titre de l&#39;espace de travail, puis cliquez sur **[!UICONTROL Work Online]**. Un X apparaît en regard de Travailler en ligne.
1. Ouvrez un espace de travail et, sur une visualisation globe, cliquez avec le bouton droit de la souris et sélectionnez le nouveau calque. Un X apparaît en regard du nom du calque.
