---
description: Si vous ne disposez pas des autorisations nécessaires pour supprimer des fichiers d’un profil ou si vous ne souhaitez pas supprimer définitivement un fichier, vous pouvez utiliser des fichiers vides (zéro octet) pour masquer les fichiers.
title: Masquer un fichier en le vidant (zéro octet)
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
exl-id: d5841fb5-afae-4352-aded-01b0b2eb9f85
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 4%

---

# Masquer un fichier en le vidant (zéro octet){#hide-a-file-by-emptying-it-zero-byte}

{{eol}}

Si vous ne disposez pas des autorisations nécessaires pour supprimer des fichiers d’un profil ou si vous ne souhaitez pas supprimer définitivement un fichier, vous pouvez utiliser des fichiers vides (zéro octet) pour masquer les fichiers.

Dans le [!DNL Profile Manager], un trait d’union (-), au lieu d’une coche, dans une colonne identifie un fichier à zéro octet.

![](assets/vis_ProfMgr_Zero-byte.png)

Contrairement aux autres méthodes de masquage des fichiers (telles que [!DNL order.txt], le paramètre Afficher et le paramètre Masqué ), Data Workbench traite les fichiers sans octet comme inexistants. Par exemple, si vous omettez une dimension qui a été utilisée dans une visualisation ou une définition de mesure, Data Workbench génère une erreur pour cette visualisation ou mesure, respectivement.

Cette fonctionnalité est utile pour plusieurs raisons, notamment lorsque vous souhaitez effectuer les opérations suivantes :

* **Rendre un fichier inutilisable** dans Data Workbench sans avoir besoin des autorisations de profil requises pour supprimer le fichier.
* **Déplacement d’une mesure, d’une dimension ou d’un filtre** à un autre emplacement sans avoir besoin des autorisations de profil requises pour supprimer le fichier de l’emplacement d’origine.
* **Masquer les éléments de menu.** Par exemple, la variable [!DNL Base] le profil a une [!DNL Metric Legend] défini dans la variable [!DNL Metric.vw] fichier . Supposons que votre société ait créé trois légendes de mesure que vous souhaitez voir apparaître dans un sous-menu Ajouter une légende > Mesure . Vous pouvez définir l’octet de la valeur [!DNL Base] profile [!DNL Metric.vw] afin que seuls votre nouveau sous-menu et trois nouvelles légendes de mesures apparaissent.

**Pour masquer un fichier**

1. Dans le [!DNL Profile Manager], ouvrez les dossiers et sous-dossiers nécessaires pour localiser le fichier dont vous souhaitez zéro octet.
1. Cliquez avec le bouton droit de la souris sur la coche en regard du nom du fichier, puis cliquez sur **[!UICONTROL Make Local]**.
1. Ouvrez le fichier local et supprimez son contenu.
1. Enregistrez le fichier, puis fermez-le.
