---
description: Procédure à suivre pour rendre un calque vectoriel disponible pour affichage dans la visualisation en globe.
title: Mise à disposition d’un nouveau calque vectoriel
uuid: 7e88f183-b0aa-452d-b124-7cd970be9bb9
exl-id: aaa1a680-3733-43c3-9d14-5aaa5f4aad6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 6%

---

# Mise à disposition d’un nouveau calque vectoriel{#making-a-new-vector-layer-available}

{{eol}}

Procédure à suivre pour rendre un calque vectoriel disponible pour affichage dans la visualisation en globe.

1. Dans le dossier d’installation Profils\*nom du profil*\Maps du répertoire d’installation du serveur Data Workbench, placez le fichier de couche et le [!DNL .vec] ou [!DNL .tsv] fichiers .
1. Modifiez la variable [!DNL order.txt] dans le dossier Profils\*nom du profil*\Mappage pour refléter l’ordre dans lequel vous souhaitez que les calques s’affichent. Par défaut, les calques apparaissent dans l’ordre lexicographique selon leur nom.

   >[!NOTE]
   >
   >Lors de la modification de la variable [!DNL order.txt] , veillez à ne pas masquer les calques de carte que vous souhaitez afficher.

   Pour plus d’informations sur l’utilisation de [!DNL order.txt] , voir le chapitre Configuration des fonctionnalités d’interface et d’analyse de *Guide de l’utilisateur de Data Workbench*.

1. Dans Data Workbench, sélectionnez le profil souhaité en cliquant avec le bouton droit sur la barre de titre de l’espace de travail, puis en cliquant sur **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Cliquez avec le bouton droit sur la barre de titre de l’espace de travail, puis cliquez sur **[!UICONTROL Work Online]**. Un X s’affiche en regard de [!DNL Work Online].
1. Ouvrez un espace de travail et, sur une visualisation en globe, cliquez avec le bouton droit de la souris et sélectionnez le nouveau calque. Un X s’affiche en regard du nom du calque.
