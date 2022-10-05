---
description: Par défaut, la fermeture d’un espace de travail déverrouillé enregistre toutes les modifications apportées à l’espace de travail.
title: Enregistrer un espace de travail
uuid: 166f9ef8-c2c4-4dfc-8d7d-453650bee6b8
exl-id: 0f1052f5-496c-443e-b29d-5973c16ef527
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---

# Enregistrer un espace de travail{#save-a-workspace}

{{eol}}

Par défaut, la fermeture d’un espace de travail déverrouillé enregistre toutes les modifications apportées à l’espace de travail.

Si l’espace de travail est un espace de travail de serveur, vos modifications ne sont enregistrées que localement, sauf si vous enregistrez spécifiquement l’espace de travail mis à jour sur le serveur de Data Workbench. Pour plus d’informations sur les espaces de travail verrouillés, voir [Déverrouillage d’un espace de travail](../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).

## Enregistrement local d’un espace de travail {#section-3f331c880f1a490c96844103c2432d61}

L’emplacement d’enregistrement par défaut est le suivant : **User\nom du profil\Espaces de travail\nom de l’onglet** dans le répertoire d’installation du Data Workbench. Par exemple, si vous travaillez avec le profil Films et que vous enregistrez un espace de travail localement à partir de la variable [!UICONTROL Custom] , l’espace de travail est enregistré dans la **User\Movies\Workspaces\Custom** dans le répertoire d’installation de votre Data Workbench.

**Pour enregistrer les modifications dans un espace de travail**

* Dans l’espace de travail, cliquez sur **[!UICONTROL File]**, puis **[!UICONTROL Save]**.

**Pour enregistrer un espace de travail existant en tant que nouvel espace de travail**

1. Sur le [!DNL Worktop] , cliquez sur la miniature de l’espace de travail à afficher.
1. Dans l’espace de travail, cliquez sur **[!UICONTROL File]**, puis cliquez sur **[!UICONTROL Save Copy As]**.
1. Dans le [!DNL Save Workspace As] , indiquez le nom et l’emplacement dans lesquels vous souhaitez enregistrer l’espace de travail copié, puis cliquez sur **[!UICONTROL Save]**.

## Enregistrement d’un espace de travail sur le serveur Data Workbench {#section-65a23da852ee4186880e002f7c87ea81}

>[!NOTE]
>
>Seuls les utilisateurs disposant des autorisations appropriées peuvent enregistrer des espaces de travail sur le serveur de Data Workbench. Pour plus d’informations, contactez votre administrateur système.

L’enregistrement des espaces de travail sur le serveur de Data Workbench connecté est également appelé publication d’un espace de travail, car il met cet espace de travail à la disposition d’autres utilisateurs. Par défaut, les espaces de travail sont enregistrés dans la variable *nom du profil de travail*\Workspaces\*nom de l’onglet* du serveur de Data Workbench. Par exemple, si vous travaillez avec le profil Films et que vous enregistrez un espace de travail sur le serveur de Data Workbench connecté à partir de la variable [!DNL Custom] , l’espace de travail est enregistré dans le dossier Films\Espaces de travail\Personnalisé du serveur de Data Workbench.

**Enregistrement d’un espace de travail sur le serveur Data Workbench**

* Sur le [!DNL Worktop] , cliquez avec le bouton droit sur la miniature de l’espace de travail que vous souhaitez enregistrer sur le serveur Data Workbench, puis cliquez sur **[!UICONTROL Save to server]**.

![](assets/mnu_workspaceManager_SaveToServerwksp.png)
