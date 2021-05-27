---
description: Si vous ne disposez pas des autorisations nécessaires pour supprimer des fichiers d’un profil ou si vous ne souhaitez pas supprimer définitivement un fichier, vous pouvez utiliser des fichiers vides (zéro octet) pour masquer les fichiers.
title: Masquer un fichier en le vidant (zéro octet)
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
exl-id: d5841fb5-afae-4352-aded-01b0b2eb9f85
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 4%

---

# Masquer un fichier en le vidant (zéro octet){#hide-a-file-by-emptying-it-zero-byte}

Si vous ne disposez pas des autorisations nécessaires pour supprimer des fichiers d’un profil ou si vous ne souhaitez pas supprimer définitivement un fichier, vous pouvez utiliser des fichiers vides (zéro octet) pour masquer les fichiers.

Dans la balise [!DNL Profile Manager], un trait d’union (-), au lieu d’une coche, dans une colonne identifie un fichier à zéro octet.

![](assets/vis_ProfMgr_Zero-byte.png)

Contrairement aux autres méthodes de masquage des fichiers (telles que [!DNL order.txt], le paramètre Afficher et le paramètre Masqué), Data Workbench traite les fichiers sans octets comme inexistants. Par exemple, si vous omettez une dimension qui a été utilisée dans une visualisation ou une définition de mesure, Data Workbench génère une erreur pour cette visualisation ou mesure, respectivement.

Cette fonctionnalité est utile pour plusieurs raisons, notamment lorsque vous souhaitez effectuer les opérations suivantes :

* **Rendez un fichier** inutilisable dans Data Workbench sans avoir besoin des autorisations de profil requises pour supprimer le fichier.
* **Déplacez une mesure, une dimension ou un** filtre vers un autre emplacement sans avoir besoin des autorisations de profil requises pour supprimer le fichier de l’emplacement d’origine.
* **Masquer les éléments de menu.** Par exemple, un  [!DNL Base] profil est  [!DNL Metric Legend] défini dans le  [!DNL Metric.vw] fichier . Supposons que votre société ait créé trois légendes de mesure que vous souhaitez voir apparaître dans un sous-menu Ajouter une légende > Mesure . Vous pouvez créer un octet pour le fichier [!DNL Base] profil [!DNL Metric.vw] de sorte que seul votre nouveau sous-menu et trois nouvelles légendes de mesure s’affichent.

**Pour masquer un fichier**

1. Dans la balise [!DNL Profile Manager], ouvrez les dossiers et sous-dossiers nécessaires pour localiser le fichier dont vous souhaitez zéro octet.
1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom du fichier et cliquez sur **[!UICONTROL Make Local]**.
1. Ouvrez le fichier local et supprimez son contenu.
1. Enregistrez le fichier, puis fermez-le.
