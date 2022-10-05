---
description: Chaque onglet ou sous-onglet du plan de travail correspond à un type particulier d’informations, telles que les tableaux de bord, l’activité, l’acquisition, etc.
title: Personnaliser un onglet de plan de travail
uuid: f1f557c8-f4cb-4789-8162-39cc7c52c943
exl-id: 529c6d8d-fc42-4c2b-a111-b8eea4665d8b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 4%

---

# Personnaliser un onglet de plan de travail{#customize-a-worktop-tab}

{{eol}}

Chaque onglet ou sous-onglet du plan de travail correspond à un type particulier d’informations, telles que les tableaux de bord, l’activité, l’acquisition, etc.

Par exemple, la variable [!DNL Acquisition] Cet onglet peut contenir des espaces de travail qui fournissent des données sur les domaines référents, les moteurs de recherche et les campagnes.

Chaque onglet qui apparaît dans la [!DNL Worktop] correspond à un dossier dans la variable *nom du profil de travail*\Espaces de travail dans le répertoire d’installation du Data Workbench. L’ordre des onglets dans la [!DNL Worktop] est contrôlé par la variable [!DNL order.txt] dans le même dossier. Par exemple, si vous avez un sous-dossier Acquisition dans le dossier Espaces de travail , vous ajoutez ensuite Acquisition comme première entrée dans la [!DNL order.txt] fichier, [!DNL Acquisition] est le premier onglet de la variable [!DNL Worktop] et tout ce qui se trouve dans ce sous-dossier s’affiche dans la variable [!DNL Acquisition] .

>[!NOTE]
>
>Pour plus d’informations sur l’utilisation de la variable [!DNL order.txt] pour personnaliser le menu de la fenêtre de l’espace de travail, voir [Personnalisation des menus](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/c-ctm-menus.md#concept-93d4c09cb7f34cd293b7b64fba1cf894).
