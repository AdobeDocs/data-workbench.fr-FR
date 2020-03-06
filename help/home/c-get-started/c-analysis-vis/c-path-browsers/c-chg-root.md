---
description: Vous pouvez modifier la racine d’un navigateur de chemins en désignant un élément affiché comme racine ou en ajoutant un nouvel élément à la visualisation.
solution: Analytics
title: Modification de la racine du navigateur de chemins
topic: Data workbench
uuid: 0bb9b004-9736-411b-bd22-cac04f4733a6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modification de la racine du navigateur de chemins{#change-the-path-browser-s-root}

Vous pouvez modifier la racine d’un navigateur de chemins en désignant un élément affiché comme racine ou en ajoutant un nouvel élément à la visualisation.

>[!NOTE]
>
>Vous ne pouvez pas définir un noeud de début ou de fin comme racine d’un navigateur de chemins d’accès.

**Pour définir la racine d’un navigateur de chemins d’accès**

* Cliquez avec le bouton droit de la souris sur l’élément souhaité, puis cliquez sur **[!UICONTROL Set as root]**.

**Pour ajouter un nouvel élément au navigateur de chemins d’accès**

1. Ouvrez un graphique ou un tableau présentant la dimension dont vous souhaitez afficher les éléments dans le navigateur de chemins.

   Par exemple, si vous travaillez avec des données de site Web, ouvrez un graphique ou un tableau de page et identifiez la page que vous souhaitez définir comme racine.

1. Appuyez sur Ctrl+Alt et faites glisser l’élément souhaité vers la position racine du navigateur de chemins.

   >[!NOTE]
   >
   >Vous pouvez modifier la dimension de base associée à un navigateur de chemins en faisant glisser un élément de la dimension souhaitée vers le navigateur de chemins. Cet élément devient la nouvelle racine du navigateur de chemins et le libellé dans le coin supérieur gauche du navigateur de chemins change pour refléter la dimension de cet élément.

   Supposons, par exemple, que vous créiez un navigateur de chemins de page affichant la séquence de pages pour chaque session. Si vous deviez faire glisser un élément de la dimension Terme de recherche vers le navigateur de chemins, l’élément de terme de recherche deviendrait la nouvelle racine et le libellé afficherait désormais la séquence de termes de recherche pour chaque session.

   >[!NOTE]
   >
   >Le fait de faire glisser un élément vers un navigateur de chemins peut modifier la dimension de base associée au navigateur de chemins, mais cela ne modifie pas la dimension de niveau, la dimension de groupe ou la mesure. Par conséquent, vous devez faire preuve de prudence lors du choix d’une dimension de base logique lorsqu’elle est utilisée avec la dimension de niveau, la dimension de groupe et la mesure du navigateur de chemins. Pour modifier la dimension de niveau, la dimension de groupe ou la mesure, vous devez modifier le [!DNL *.vw] fichier du navigateur de chemins dans un éditeur de texte tel que le Bloc-notes. Voir [Configuration des navigateurs](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3)de chemin d’accès.

