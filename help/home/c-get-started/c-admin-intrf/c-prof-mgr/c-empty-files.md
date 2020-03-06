---
description: Si vous n’êtes pas autorisé à supprimer des fichiers d’un profil ou si vous ne souhaitez pas supprimer définitivement un fichier, vous pouvez utiliser des fichiers vides (zéro octet) pour masquer les fichiers.
solution: Analytics
title: Masquer un fichier en le vidant (zéro octet)
topic: Data workbench
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Masquer un fichier en le vidant (zéro octet){#hide-a-file-by-emptying-it-zero-byte}

Si vous n’êtes pas autorisé à supprimer des fichiers d’un profil ou si vous ne souhaitez pas supprimer définitivement un fichier, vous pouvez utiliser des fichiers vides (zéro octet) pour masquer les fichiers.

Dans la colonne [!DNL Profile Manager], un trait d’union (-), au lieu d’une coche, identifie un fichier à zéro octet.

![](assets/vis_ProfMgr_Zero-byte.png)

Contrairement aux autres méthodes de masquage des fichiers (par exemple, [!DNL order.txt]le paramètre Afficher et le paramètre Masqué), les outils de données considèrent les fichiers à 0 octet comme inexistants. Par exemple, si vous utilisez une dimension à zéro octet dans une visualisation ou une définition de mesure, les Outils de données génèrent une erreur pour cette visualisation ou mesure, respectivement.

Cette fonctionnalité est utile pour plusieurs raisons, notamment lorsque vous souhaitez effectuer les opérations suivantes :

* **Rendre un fichier inutilisable** dans les Outils de données sans avoir besoin des autorisations de profil requises pour supprimer le fichier.
* **Déplacez une mesure, une dimension ou un filtre** vers un autre emplacement sans avoir besoin des autorisations de profil requises pour supprimer le fichier de l’emplacement d’origine.
* **Masquer les options de menu.** Par exemple, un [!DNL Base] profil est [!DNL Metric Legend] défini dans le [!DNL Metric.vw] fichier. Supposons que votre entreprise ait créé trois légendes de mesure que vous souhaitez voir apparaître dans un sous-menu Ajouter une légende > Mesure. Vous pouvez attribuer un octet zéro au [!DNL Base] fichier [!DNL Metric.vw] de profil afin que seuls votre nouveau sous-menu et trois nouvelles légendes de mesure apparaissent.

**Pour masquer un fichier**

1. Dans la [!DNL Profile Manager]section, ouvrez les dossiers et sous-dossiers nécessaires pour localiser le fichier à zéro octet.
1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom du fichier, puis cliquez sur **[!UICONTROL Make Local]**.
1. Ouvrez le fichier local et supprimez son contenu.
1. Enregistrez et fermez le fichier.

