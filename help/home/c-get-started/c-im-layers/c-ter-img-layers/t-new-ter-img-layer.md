---
description: Procédure à suivre pour rendre n’importe quelle couche de terrain disponible pour affichage dans la visualisation du globe.
title: Mettre à disposition un nouveau calque d’image du terrain
uuid: 8fb98a3e-6335-4922-a1e6-35c92b19e2ec
exl-id: bf0e6b37-4c8a-4d50-8bc9-eb70ca1cbb23
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 7%

---

# Mettre à disposition un nouveau calque d’image du terrain{#make-a-new-terrain-image-layer-available}

{{eol}}

Procédure à suivre pour rendre n’importe quelle couche de terrain disponible pour affichage dans la visualisation du globe.

1. Dans le dossier Profils\*nom du profil*\Maps du répertoire d’installation du serveur Data Workbench, placez le fichier de couche et les fichiers image pris en charge.
1. Modifiez la variable [!DNL order.txt] dans le dossier Profils\*nom du profil*\Mappage pour refléter l’ordre dans lequel vous souhaitez que les calques s’affichent. Par défaut, les calques apparaissent dans l’ordre lexicographique selon leur nom.

   >[!NOTE]
   >
   >Lors de la modification de la variable [!DNL order.txt] , veillez à ne pas masquer les calques de carte que vous souhaitez afficher.

   Pour plus d’informations sur l’utilisation de [!DNL order.txt] , voir le chapitre Configuration des fonctionnalités d’interface et d’analyse de *Guide de l’utilisateur de Data Workbench*.

1. Dans Data Workbench, sélectionnez le profil souhaité en cliquant avec le bouton droit de la souris sur la barre de titre de l’espace de travail, puis en cliquant sur **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Cliquez avec le bouton droit sur la barre de titre de l’espace de travail, puis cliquez sur **[!UICONTROL Work Online]**. Un X apparaît en regard de l’option Travail en ligne.
1. Ouvrez un espace de travail et, sur une visualisation en globe, cliquez avec le bouton droit de la souris et sélectionnez le nouveau calque. Un X s’affiche en regard du nom du calque.
