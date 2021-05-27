---
description: Procédure à suivre pour rendre un calque de point d’élément disponible pour affichage dans la visualisation en globe.
title: Mise à disposition d’un nouveau calque de point d’élément
uuid: 7880de63-d206-4c56-b8cf-75882d867ace
exl-id: 9001f6b6-5d25-48a0-9381-04f679e0ff4d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 6%

---

# Mise à disposition d’un nouveau calque de point d’élément{#making-a-new-element-point-layer-available}

Procédure à suivre pour rendre un calque de point d’élément disponible pour affichage dans la visualisation en globe.

1. Dans le dossier d’installation Profils\*nom du profil*\Maps du répertoire d’installation du serveur Data Workbench, placez le fichier de couche et son fichier de recherche associé.
1. Si vous avez défini une nouvelle dimension pour votre calque de point d’élément et que vous n’avez pas encore retransformé votre jeu de données, retransformez votre jeu de données maintenant.
1. Modifiez le fichier [!DNL order.txt] dans le dossier Profils\*nom du profil*\Maps afin de refléter l’ordre dans lequel vous souhaitez que les calques s’affichent. Par défaut, les calques apparaissent dans l’ordre lexicographique selon leur nom.

   >[!NOTE]
   >
   >Lors de la modification du fichier [!DNL order.txt], veillez à ne pas masquer les calques de carte que vous souhaitez afficher.

   Pour plus d’informations sur l’utilisation des fichiers [!DNL order.txt], consultez le chapitre Configuration de l’interface et des fonctionnalités d’analyse du *Guide de l’utilisateur du Data Workbench*.

1. Dans Data Workbench, sélectionnez le profil souhaité en cliquant avec le bouton droit sur la barre de titre de l’espace de travail, puis en cliquant sur **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]***.
1. Cliquez avec le bouton droit sur la barre de titre de l’espace de travail, puis cliquez sur **[!UICONTROL Work Online]**. Un X apparaît en regard de [!DNL Work Online].
1. Ouvrez un espace de travail et, sur une visualisation en globe, cliquez avec le bouton droit de la souris et sélectionnez le nouveau calque. Un X s’affiche en regard du nom du calque.
