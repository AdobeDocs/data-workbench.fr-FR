---
description: Cette section décrit la procédure à suivre pour rendre un calque de point d’élément disponible pour l’affichage sur la visualisation du globe.
title: Mise à disposition d’un nouveau calque de point d’élément
uuid: 7880de63-d206-4c56-b8cf-75882d867ace
exl-id: 9001f6b6-5d25-48a0-9381-04f679e0ff4d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 6%

---

# Mise à disposition d’un nouveau calque de point d’élément{#making-a-new-element-point-layer-available}

Cette section décrit la procédure à suivre pour rendre un calque de point d’élément disponible pour l’affichage sur la visualisation du globe.

1. Dans le dossier Profils\*nom du profil*\Maps du répertoire d’installation du serveur de l’outil de données, placez le fichier de calque et le fichier de recherche correspondant.
1. Si vous avez défini une nouvelle dimension pour votre calque de point d’élément et que vous n’avez pas encore transformé votre jeu de données, retransformez votre jeu de données maintenant.
1. Modifiez le fichier [!DNL order.txt] dans le dossier Profils\*nom du profil*\Maps afin de refléter l’ordre dans lequel les calques doivent s’afficher. Par défaut, les calques apparaissent par leur nom dans l’ordre lexicographique.

   >[!NOTE]
   >
   >Lorsque vous modifiez le fichier [!DNL order.txt], veillez à ne pas masquer les calques de mappage que vous souhaitez afficher.

   Pour plus d&#39;informations sur l&#39;utilisation des fichiers [!DNL order.txt], consultez le chapitre Configuration des fonctionnalités d&#39;interface et d&#39;Analyse du *Guide de l&#39;utilisateur Data Workbench*.

1. Dans les outils de données, sélectionnez le profil de votre choix en cliquant avec le bouton droit sur la barre de titre de l’espace de travail et en cliquant sur **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]***.
1. Cliquez avec le bouton droit sur la barre de titre de l&#39;espace de travail, puis cliquez sur **[!UICONTROL Work Online]**. Un X apparaît en regard de [!DNL Work Online].
1. Ouvrez un espace de travail et, sur une visualisation globe, cliquez avec le bouton droit de la souris et sélectionnez le nouveau calque. Un X apparaît en regard du nom du calque.
