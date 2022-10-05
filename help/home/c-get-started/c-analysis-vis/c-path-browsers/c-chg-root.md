---
description: Vous pouvez modifier la racine d’un navigateur de chemins d’accès en désignant un élément affiché comme racine ou en ajoutant un nouvel élément à la visualisation.
title: Modification de la racine du navigateur d’un chemin d’accès
uuid: 0bb9b004-9736-411b-bd22-cac04f4733a6
exl-id: 09842b93-af26-42b9-9395-a02b86978b21
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---

# Modification de la racine du navigateur d’un chemin d’accès{#change-the-path-browser-s-root}

{{eol}}

Vous pouvez modifier la racine d’un navigateur de chemins d’accès en désignant un élément affiché comme racine ou en ajoutant un nouvel élément à la visualisation.

>[!NOTE]
>
>Vous ne pouvez pas définir un noeud de début ou de fin comme racine d’un navigateur de chemins d’accès.

**Pour définir la racine d’un navigateur de chemins d’accès**

* Cliquez avec le bouton droit de la souris sur l’élément souhaité, puis cliquez sur **[!UICONTROL Set as root]**.

**Pour ajouter un nouvel élément à l’explorateur de chemins d’accès**

1. Ouvrez un graphique ou un tableau présentant la dimension dont vous souhaitez afficher les éléments dans l’explorateur de chemins d’accès.

   Par exemple, si vous utilisez des données de site web, ouvrez un graphique ou un tableau de page et identifiez la page que vous souhaitez définir comme racine.

1. Appuyez sur Ctrl+Alt et faites glisser l’élément souhaité vers la position racine dans l’explorateur de chemins d’accès.

   >[!NOTE]
   >
   >Vous pouvez modifier la dimension de base associée à un navigateur de chemins d’accès en faisant glisser un élément de la dimension souhaitée vers l’explorateur de chemins d’accès. Cet élément devient la nouvelle racine de l’explorateur de chemins d’accès et le libellé dans le coin supérieur gauche de l’explorateur de chemins d’accès change pour refléter la dimension de cet élément.

   Supposons, par exemple, que vous créiez un navigateur de chemins de page affichant la séquence de pages pour chaque session. Si vous deviez faire glisser un élément de la dimension Terme de recherche vers l’explorateur de chemins d’accès, l’élément de terme de recherche deviendrait la nouvelle racine et le libellé afficherait désormais la Séquence de termes de recherche pour chaque session.

   >[!NOTE]
   >
   >Le fait de faire glisser un élément vers un navigateur de chemins d’accès peut modifier la dimension de base associée à l’explorateur de chemins d’accès, mais cela ne modifie pas la dimension de niveau, la dimension de groupe ou la mesure. Par conséquent, vous devez être prudent lors du choix d’une dimension de base qui est logique lorsqu’elle est utilisée avec la dimension de niveau, la dimension de groupe et la mesure du navigateur de chemins d’accès. Pour modifier la dimension de niveau, la dimension de groupe ou la mesure, vous devez modifier le [!DNL *.vw] dans un éditeur de texte tel que le Bloc-notes. Voir [Configuration des navigateurs de chemins d’accès](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).
