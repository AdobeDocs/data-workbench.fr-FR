---
description: Cette section décrit la procédure à suivre pour rendre un calque de point d’élément disponible pour l’affichage sur la visualisation du globe.
solution: Analytics
title: Mise à disposition d’un nouveau calque de point d’élément
topic: Data workbench
uuid: 7880de63-d206-4c56-b8cf-75882d867ace
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mise à disposition d’un nouveau calque de point d’élément{#making-a-new-element-point-layer-available}

Cette section décrit la procédure à suivre pour rendre un calque de point d’élément disponible pour l’affichage sur la visualisation du globe.

1. Dans le dossier Profils\*nom du profil*\Mappages du répertoire d’installation du serveur de l’outil de données, importez le fichier de calque et le fichier de recherche associé.
1. Si vous avez défini une nouvelle dimension pour votre calque de point d’élément et que vous n’avez pas encore retransformé votre jeu de données, retransformez votre jeu de données maintenant.
1. Modifiez le [!DNL order.txt] fichier dans le dossier Profils\*nom du profil*\Mappages afin de refléter l’ordre dans lequel vous souhaitez que les calques s’affichent. Par défaut, les calques apparaissent par leur nom dans l’ordre lexicographique.

   >[!NOTE]
   >
   >Lorsque vous modifiez le [!DNL order.txt] fichier, veillez à ne pas couvrir les calques de mappage que vous souhaitez afficher.

   Pour plus d’informations sur l’utilisation des [!DNL order.txt] fichiers, voir le chapitre Configuration des fonctionnalités d’interface et d’analyse du Guide *de l’utilisateur des outils de* données.

1. Dans les outils de données, sélectionnez le profil souhaité en cliquant avec le bouton droit sur la barre de titre de l’espace de travail et en cliquant sur **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Cliquez avec le bouton droit sur la barre de titre de l’espace de travail, puis cliquez sur **[!UICONTROL Work Online]**. Un X apparaît en regard de [!DNL Work Online].
1. Ouvrez un espace de travail et, sur une visualisation sur un globe, cliquez avec le bouton droit de la souris et sélectionnez le nouveau calque. Un X apparaît en regard du nom du calque.
