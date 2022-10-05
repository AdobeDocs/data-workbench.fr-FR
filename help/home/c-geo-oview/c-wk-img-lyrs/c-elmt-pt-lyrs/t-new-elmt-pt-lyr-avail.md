---
description: Procédure à suivre pour rendre un calque de point d’élément disponible pour affichage dans la visualisation en globe.
title: Mise à disposition d’un nouveau calque de point d’élément
uuid: 7880de63-d206-4c56-b8cf-75882d867ace
exl-id: 9001f6b6-5d25-48a0-9381-04f679e0ff4d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 6%

---

# Mise à disposition d’un nouveau calque de point d’élément{#making-a-new-element-point-layer-available}

{{eol}}

Procédure à suivre pour rendre un calque de point d’élément disponible pour affichage dans la visualisation en globe.

1. Dans le dossier d’installation Profils\*nom du profil*\Maps du répertoire d’installation du serveur Data Workbench, placez le fichier de couche et son fichier de recherche associé.
1. Si vous avez défini une nouvelle dimension pour votre calque de point d’élément et que vous n’avez pas encore retransformé votre jeu de données, retransformez votre jeu de données maintenant.
1. Modifiez la variable [!DNL order.txt] dans le dossier Profils\*nom du profil*\Mappage pour refléter l’ordre dans lequel vous souhaitez que les calques s’affichent. Par défaut, les calques apparaissent dans l’ordre lexicographique selon leur nom.

   >[!NOTE]
   >
   >Lors de la modification de la variable [!DNL order.txt] , veillez à ne pas masquer les calques de carte que vous souhaitez afficher.

   Pour plus d’informations sur l’utilisation de [!DNL order.txt] , voir le chapitre Configuration des fonctionnalités d’interface et d’analyse de *Guide de l’utilisateur de Data Workbench*.

1. Dans Data Workbench, sélectionnez le profil souhaité en cliquant avec le bouton droit sur la barre de titre de l’espace de travail, puis en cliquant sur **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Cliquez avec le bouton droit sur la barre de titre de l’espace de travail, puis cliquez sur **[!UICONTROL Work Online]**. Un X s’affiche en regard de [!DNL Work Online].
1. Ouvrez un espace de travail et, sur une visualisation en globe, cliquez avec le bouton droit de la souris et sélectionnez le nouveau calque. Un X s’affiche en regard du nom du calque.
