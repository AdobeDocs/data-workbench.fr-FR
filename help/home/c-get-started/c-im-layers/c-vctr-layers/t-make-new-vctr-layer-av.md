---
description: Procédure à suivre pour rendre n’importe quel calque vectoriel disponible à afficher sur la visualisation du globe.
title: Mettre à disposition un nouveau calque vectoriel
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
exl-id: 6c084bac-1a6d-452a-bf07-e502d0f2145a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 7%

---

# Mettre à disposition un nouveau calque vectoriel{#make-a-new-vector-layer-available}

{{eol}}

Procédure à suivre pour rendre n’importe quel calque vectoriel disponible à afficher sur la visualisation du globe.

1. Dans le dossier d’installation Profils\*nom du profil*\Maps du répertoire d’installation du serveur Data Workbench, placez le fichier de couche et le [!DNL .vec] ou [!DNL .tsv] fichiers .
1. Modifiez la variable [!DNL order.txt] dans le dossier Profils\*nom du profil*\Mappage pour refléter l’ordre dans lequel vous souhaitez que les calques s’affichent. Par défaut, les calques apparaissent dans l’ordre lexicographique selon leur nom.

   >[!NOTE]
   >
   >Lors de la modification de la variable [!DNL order.txt] , veillez à ne pas masquer les calques de carte que vous souhaitez afficher.

   Pour plus d’informations sur l’utilisation de [!DNL order.txt] fichiers, voir [Personnalisation des menus à l’aide des fichiers Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

1. Dans Insight, sélectionnez le profil souhaité en cliquant avec le bouton droit sur la barre de titre de l’espace de travail, puis en cliquant sur **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Cliquez avec le bouton droit sur la barre de titre de l’espace de travail, puis cliquez sur **[!UICONTROL Work Online]**. Un X apparaît en regard de l’option Travail en ligne.
1. Ouvrez un espace de travail et, sur une visualisation en globe, cliquez avec le bouton droit de la souris et sélectionnez le nouveau calque. Un X s’affiche en regard du nom du calque.
