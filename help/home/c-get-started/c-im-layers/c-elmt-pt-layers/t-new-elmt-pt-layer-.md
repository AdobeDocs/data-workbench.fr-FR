---
description: Cette section décrit la procédure à suivre pour rendre n’importe quel calque de point d’élément disponible à afficher sur la visualisation sur le globe.
solution: Analytics
title: Rendre un nouveau calque de point d’élément disponible
topic: Data workbench
uuid: 5f4bad2f-e98d-4224-bba8-285ad5e23da9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Rendre un nouveau calque de point d’élément disponible{#make-a-new-element-point-layer-available}

Cette section décrit la procédure à suivre pour rendre n’importe quel calque de point d’élément disponible à afficher sur la visualisation sur le globe.

1. Dans le dossier Profils\*nom du profil*\Mappages du répertoire d’installation du serveur Outils de données, importez le fichier de calque et le fichier de recherche associé.
1. Si vous avez défini une nouvelle dimension pour votre calque de point d’élément et que vous n’avez pas encore retransformé votre jeu de données, retransformez votre jeu de données maintenant.
1. Modifiez le [!DNL order.txt] fichier dans le dossier Profils\*nom du profil*\Mappages afin de refléter l’ordre dans lequel vous souhaitez que les calques s’affichent. Par défaut, les calques apparaissent par leur nom dans l’ordre lexicographique.

   >[!NOTE]
   >
   >Lorsque vous modifiez le [!DNL order.txt] fichier, veillez à ne pas couvrir les calques de mappage que vous souhaitez afficher.

   Pour plus d’informations sur l’utilisation des [!DNL order.txt] fichiers, voir le chapitre Configuration des fonctionnalités d’interface et d’analyse du Guide *de l’utilisateur des outils de* données.

1. Dans Outils de données, sélectionnez le profil souhaité en cliquant avec le bouton droit sur la barre de titre de l’espace de travail et en cliquant sur **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Cliquez avec le bouton droit sur la barre de titre de l’espace de travail, puis cliquez sur **[!UICONTROL Work Online]**. Un X apparaît en regard de Travailler en ligne.
1. Ouvrez un espace de travail et, sur une visualisation sur un globe, cliquez avec le bouton droit de la souris et sélectionnez le nouveau calque. Un X apparaît en regard du nom du calque.
